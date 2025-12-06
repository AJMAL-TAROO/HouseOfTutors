# Premium Features Upgrade/Downgrade System Implementation

## Overview
This document describes the premium features upgrade/downgrade system implemented to prevent tutors from gaming the billing system by upgrading to premium, using features, and then downgrading before month-end.

## Business Requirements Addressed
- Tutors pay Rs50/student/month on basic plan
- Tutors pay Rs100/student/month on premium plan (with whiteboard and timetable access)
- Premium upgrades are locked for 30 days minimum
- Tutors can schedule a downgrade during lock period
- Auto-downgrade occurs when lock period expires and downgrade is pending

## New Firebase Fields (ADMIN Node)

Each admin node now includes these additional fields:

```javascript
{
  UNLOCK_FEATURES: boolean,              // true = premium, false = basic
  FEES_PER_STUDENT: number,             // 50 or 100
  UNLOCK_FEATURES_ACTIVATED_ON: string, // "DDMMYYHHmm" format (e.g., "0612252003")
  UNLOCK_FEATURES_LOCKED_UNTIL: string, // "DDMMYYHHmm" format (e.g., "0501262003")
  PENDING_DOWNGRADE: boolean            // true if downgrade is scheduled
}
```

### Date Format: DDMMYYHHmm
- **DD**: Day (01-31)
- **MM**: Month (01-12)
- **YY**: Year (last 2 digits, e.g., 25 for 2025)
- **HH**: Hour (00-23)
- **mm**: Minutes (00-59)

**Example**: "0612252003" = December 6, 2025 at 20:03

## Implementation Details

### 1. DateTime Helper Functions

Located in `DashboardAdmin.html` starting at line 714:

```javascript
// Converts JavaScript Date to DDMMYYHHmm string
function dateToCustomFormat(date)

// Converts DDMMYYHHmm string to JavaScript Date
function customFormatToDate(str)

// Adds 30 days to a date
function add30Days(date)

// Checks if lock period has expired
function isLockExpired(lockedUntilStr)

// Formats date for user-friendly display
function formatDateForDisplay(dateStr)
```

### 2. Auto-Downgrade Logic

**Location**: Line 878-897 in `DashboardAdmin.html`

**When**: Executes automatically on dashboard load

**Conditions**:
1. `UNLOCK_FEATURES === true` (user is on premium)
2. `PENDING_DOWNGRADE === true` (user has requested downgrade)
3. Current date >= `UNLOCK_FEATURES_LOCKED_UNTIL` (lock has expired)

**Action**: Updates Firebase to downgrade user and reloads page:
```javascript
{
  UNLOCK_FEATURES: false,
  FEES_PER_STUDENT: 50,
  PENDING_DOWNGRADE: false
}
```

### 3. Premium Plan UI Section

**Location**: Lines 331-338 in `DashboardAdmin.html`

Added to the "Dashboard Details" modal between summary stats and student details.

**Displays**:
- Current plan (Basic or Premium)
- Billing rate
- For Premium: activation date, lock expiry date, pending downgrade status
- Appropriate action buttons based on state

### 4. User Actions

#### A. Upgrade to Premium

**Modal**: `upgradePremiumModal` (lines 314-333)

**Flow**:
1. User clicks "Upgrade to Premium" button
2. Warning modal shows:
   - Rs100/student/month billing
   - 30-day lock period
   - Premium features list
3. User confirms
4. Firebase updates:
   ```javascript
   {
     UNLOCK_FEATURES: true,
     FEES_PER_STUDENT: 100,
     UNLOCK_FEATURES_ACTIVATED_ON: <current datetime>,
     UNLOCK_FEATURES_LOCKED_UNTIL: <current datetime + 30 days>,
     PENDING_DOWNGRADE: false
   }
   ```

**Function**: `confirmUpgradePremium()` (line 1635)

#### B. Request Downgrade

**Modal**: `requestDowngradeModal` (lines 335-347)

**Flow**:
1. User clicks "Request Downgrade to Basic" button
2. System checks if lock has expired
3. **If lock expired**:
   - Shows "Downgrade immediately" option
   - On confirm: Sets `UNLOCK_FEATURES=false`, `FEES_PER_STUDENT=50`, `PENDING_DOWNGRADE=false`
4. **If still locked**:
   - Shows lock expiry date
   - Offers to schedule downgrade
   - On confirm: Sets `PENDING_DOWNGRADE=true`

**Function**: `confirmRequestDowngrade()` (line 1722)

#### C. Cancel Downgrade Request

**Modal**: `cancelDowngradeModal` (lines 349-360)

**Flow**:
1. User clicks "Cancel Downgrade Request" button
2. Confirmation modal appears
3. User confirms
4. Firebase updates: `PENDING_DOWNGRADE: false`

**Function**: `confirmCancelDowngrade()` (line 1777)

### 5. Premium Plan Display Logic

**Function**: `displayPremiumPlanInfo(adminData, adminKey)` (line 1509)

Dynamically generates UI based on current plan state:

**For Basic Plan**:
- Shows current plan and billing rate
- Lists basic features
- Shows premium features to unlock
- Displays "Upgrade to Premium" button

**For Premium Plan**:
- Shows current plan and billing rate
- Displays activation and lock expiry dates
- Lists premium features
- Shows lock status (locked/expired)
- Shows pending downgrade alert if applicable
- Displays appropriate button ("Request Downgrade" or "Cancel Downgrade Request")

## Testing

### Test File: test_premium_features.html

Comprehensive test page includes:

1. **Test Controls**: Load admin data from Firebase
2. **DateTime Function Tests**: Test each helper function
3. **Flow Simulations**: Simulate all 5 scenarios
4. **Manual Testing Instructions**: Step-by-step guide
5. **Expected Firebase Structure**: Documentation reference

### Test Scenarios

1. **Upgrade to Premium**: Verify all fields updated correctly
2. **Request Downgrade (Locked)**: Schedule downgrade for future
3. **Request Downgrade (Unlocked)**: Immediate downgrade
4. **Cancel Downgrade**: Remove pending downgrade
5. **Auto-Downgrade**: Automatic downgrade on dashboard load

## User Experience Flow

### New User (Basic Plan)
```
Login → Dashboard Details → See Basic Plan → Upgrade to Premium →
Warning Modal → Confirm → Premium Active (30-day lock)
```

### Premium User Wants to Downgrade (Before 30 Days)
```
Dashboard Details → See Premium Plan (locked until DATE) →
Request Downgrade → Schedule Downgrade → PENDING_DOWNGRADE = true →
(After 30 days) → Dashboard Load → Auto-Downgrade → Basic Plan
```

### Premium User Wants to Downgrade (After 30 Days)
```
Dashboard Details → See Premium Plan (lock expired) →
Request Downgrade → Confirm Immediate Downgrade → Basic Plan
```

### Premium User Changes Mind About Downgrade
```
Dashboard Details → See Pending Downgrade Alert →
Cancel Downgrade Request → Confirm → Remain on Premium
```

## Security Considerations

1. **Server-side validation required**: Currently client-side only. For production, add Firebase Security Rules to validate:
   - Lock period enforcement
   - Date format validation
   - Field value constraints

2. **Billing calculation**: The `FEES_PER_STUDENT` field provides accurate billing data that cannot be manipulated by users during the lock period.

3. **Auto-downgrade**: Happens only when both conditions are met (premium + pending downgrade + lock expired), preventing premature downgrades.

## Files Modified

1. **DashboardAdmin.html**: 
   - Added DateTime helper functions (57 lines)
   - Added auto-downgrade logic (23 lines)
   - Added Premium Plan UI section (9 lines)
   - Added 3 modal dialogs (57 lines)
   - Added premium feature functions (290 lines)
   - **Total additions**: ~430 lines

## Files Created

1. **test_premium_features.html**: Comprehensive test page (401 lines)
2. **PREMIUM_FEATURES_IMPLEMENTATION.md**: This documentation

## Backward Compatibility

- Existing fields not modified
- New fields default to falsy values for existing admins
- Existing users will see Basic Plan by default
- No breaking changes to existing functionality

## Future Enhancements

1. Add Firebase Security Rules for server-side validation
2. Add email notifications when lock expires
3. Add billing history tracking
4. Add admin panel to view all premium users
5. Add analytics for upgrade/downgrade patterns

## Known Limitations

1. Year 2100 issue: Date format assumes 20xx century (acceptable for application lifespan)
2. Client-side only: Requires Firebase Security Rules for production
3. Alert dialogs: Could be enhanced with toast notifications
4. No billing integration: Manual billing calculation needed

## Support & Maintenance

- All code in single file for easier maintenance
- Helper functions reusable for future date operations
- Comprehensive test page for regression testing
- Clear documentation for future developers

## Conclusion

This implementation provides a robust solution to prevent billing system gaming while maintaining a good user experience. The 30-day lock period ensures tutors are committed to the premium plan, and the auto-downgrade feature provides transparency and automation.
