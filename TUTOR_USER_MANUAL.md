# House of Tutors - Tutor User Manual
## Complete Guide for Daily Usage

**Version:** 1.0  
**Last Updated:** January 2026  
**Platform:** House of Tutors Online Tutoring System

---

## Table of Contents

1. [Getting Started](#1-getting-started)
2. [Dashboard Overview](#2-dashboard-overview)
3. [Classroom Management](#3-classroom-management)
4. [Student Management](#4-student-management)
5. [Timetable Management](#5-timetable-management)
6. [Notes & Homework Management](#6-notes--homework-management)
7. [Communication Features](#7-communication-features)
8. [Virtual Classroom & Online Classes](#8-virtual-classroom--online-classes)
9. [Premium Features & Billing](#9-premium-features--billing)
10. [Profile Management](#10-profile-management)
11. [Student Attendance Tracking](#11-student-attendance-tracking)
12. [Troubleshooting & FAQs](#12-troubleshooting--faqs)

---

## 1. Getting Started

### 1.1 Account Registration

1. **Navigate** to the House of Tutors website
2. **Click** on "Sign up" link from the login page
3. **Choose** "Tutor/Admin" account type
4. **Fill in** the registration form:
   - Email address
   - Password (secure password recommended)
   - Full name
   - Contact information
5. **Submit** your registration
6. **Wait for approval** - Your account will be reviewed by administrators

> **Note:** New tutor accounts are set to "pending" status by default. You will be contacted once your account is approved.

### 1.2 First Time Login

1. **Visit** the login page (Login.html)
2. **Enter** your registered email and password
3. **Click** "Sign in"

**If your account is pending approval:**
- You will see an overlay message: "Account's approval is still pending. When approved, you will be contacted. Thank you."
- The dashboard will be locked until approval

**After approval:**
- You will have full access to the tutor dashboard
- Set up your profile (recommended)
- Configure your first classroom

### 1.3 Understanding Account Levels

**Basic Plan (Default):**
- Cost: Rs 50 per student per month
- Access to core features
- Classroom management
- Student management
- Notes upload
- Comments and feedback

**Premium Plan:**
- Cost: Rs 100 per student per month
- All Basic features PLUS:
- Whiteboard access
- Timetable management
- Advanced scheduling tools
- 30-day lock-in period applies

---

## 2. Dashboard Overview

### 2.1 Accessing Your Dashboard

After login, you'll arrive at the **Admin Dashboard** (DashboardAdmin.html) - your control center for managing all tutoring activities.

### 2.2 Dashboard Layout

**Navigation Bar (Top):**
- **Left:** Menu button (hamburger icon) - Opens side drawer
- **Center:** "House Of Tutors" logo/title
- **Right:** Quick access buttons
  - Profile icon
  - Info button (dashboard statistics)
  - Logout button

**Main Content Area:**
- Grid of classroom cards (up to 3 per row on desktop)
- "Add Classroom" card (purple with plus icon)
- Scrollable content area

**Side Drawer Menu:**
Access via hamburger menu button, includes:
- Create Classroom
- Add Student to Classroom
- Remove Student from Classroom
- Upload Notes
- Add Session for Timetable (Premium)
- Delete Session from Timetable (Premium)
- View My Timetable (Premium)
- Student Attendance
- Customer Support

**Background Customization:**
- **"Change Background" button** (bottom-right, fixed position)
- Choose from various background options
- Personalize your workspace

### 2.3 Dashboard Information Modal

**Access:** Click the "info" icon in the navbar

**Displays:**
- Total number of classrooms
- Total number of students across all classrooms
- Your email address
- Registration date
- Premium plan status and details
- Customer support contact (WhatsApp: +23057882383)

### 2.4 Super User Access

For administrators with elevated permissions:
- Access super user features via navbar button
- Manage system-wide settings
- Advanced administrative controls

---

## 3. Classroom Management

Classrooms are the core organizational unit in House of Tutors. Each classroom represents a group of students you're teaching.

### 3.1 Creating a New Classroom

**Method 1: From Dashboard**
1. Click the **"Add Classroom"** card (purple card with plus icon)
2. Enter classroom details in the modal:
   - **Classroom Name** (e.g., "Math Grade 10", "Physics Advanced")
   - **Virtual Room URLs** (one per line)
3. Click **"Create"**
4. Dashboard refreshes with new classroom

**Method 2: From Side Drawer**
1. Open side drawer (hamburger menu)
2. Select **"Create Classroom"**
3. Fill in details
4. Submit

**Virtual Room URLs:**
- Add links to your virtual meeting rooms (Zoom, Google Meet, etc.)
- One URL per line
- Students will access these for online classes

### 3.2 Viewing Classroom Details

**Each classroom card shows:**
- Classroom name
- Number of enrolled students
- Action buttons:
  - **View/Edit** (pencil icon) - Manage classroom
  - **Delete** (trash icon) - Remove classroom
  - **Join VR** (if virtual rooms configured) - Enter virtual classroom

**Card Actions:**
- **Click card** to view details
- **Hover** for visual feedback (darker purple)

### 3.3 Editing a Classroom

1. Click the **edit/pencil icon** on classroom card
2. Modify details:
   - Change classroom name
   - Add/remove virtual room URLs
   - Update configuration
3. Click **"Update"**
4. Changes saved immediately

### 3.4 Deleting a Classroom

1. Click the **delete/trash icon** on classroom card
2. **Confirm deletion** in the modal
3. Classroom and all associated data will be removed

> **⚠️ Warning:** Deleting a classroom removes:
> - All student enrollments
> - Classroom comments
> - Associated notes (if classroom-specific)
> - Timetable sessions
> 
> This action cannot be undone!

### 3.5 Classroom Organization Tips

- **Use descriptive names:** Include subject, level, or time (e.g., "English 101 - Morning")
- **Limit classroom size:** Keep student numbers manageable
- **Regular updates:** Review and update virtual room links
- **Archive old classrooms:** Delete completed courses to keep dashboard clean

---

## 4. Student Management

### 4.1 Adding Students to a Classroom

**From Side Drawer:**
1. Open side drawer
2. Select **"Add Student to Classroom"**
3. Choose the **target classroom** from dropdown
4. Select **student(s)** to add
5. Click **"Add"**

**Important Notes:**
- Students must be registered in the system first
- One student can be enrolled in multiple classrooms
- Students immediately gain access to classroom materials

### 4.2 Viewing Students in a Classroom

**Method 1: Dashboard Info Modal**
1. Click info button in navbar
2. Scroll to student list
3. View all students across classrooms

**Method 2: Through Comments Section**
1. Access classroom comments (AddCommentToClassroom.html)
2. View student activity and participation

### 4.3 Removing Students from a Classroom

**From Side Drawer:**
1. Open side drawer
2. Select **"Remove Student from Classroom"**
3. Choose the **classroom**
4. Select **student(s)** to remove
5. Click **"Remove"**
6. Confirm action

**Effects of Removal:**
- Student loses access to classroom materials
- Previous submissions and comments remain
- Can be re-added later if needed

### 4.4 Managing Student Details

**Access:** ModifyStudentDetails.html

**Can modify:**
- Student name
- Contact information
- Parent/guardian details
- Academic level
- Notes about student

**To modify:**
1. Access student management section
2. Select student
3. Edit required fields
4. Save changes

### 4.5 Creating New Student Accounts

**Access:** CreateStudent.html via administrative functions

**Required Information:**
- Student email (for login)
- Student name
- Password (generated or set)
- Additional details as needed

**Process:**
1. Fill in student registration form
2. Set initial password
3. Submit to create account
4. Share credentials with student/parent

---

## 5. Timetable Management

> **🌟 Premium Feature** - Requires Premium Plan subscription

Timetable management helps you organize and schedule your teaching sessions systematically.

### 5.1 Viewing Your Timetable

**Access:**
1. Open side drawer
2. Select **"View My Timetable"** (MyTimeTable.html)

**Timetable Display:**
- Weekly view of all scheduled sessions
- Date and time for each session
- Classroom association
- Session type/subject

### 5.2 Adding a Session to Timetable

**Access:**
1. Open side drawer
2. Select **"Add Session for Timetable"** (AddSessionForTimetable.html)

**Steps:**
1. **Select classroom** for the session
2. **Enter session details:**
   - Session name/title
   - Subject
   - Date
   - Start time
   - End time
   - Description (optional)
3. **Set recurrence** (if applicable):
   - One-time session
   - Weekly recurring
   - Custom schedule
4. Click **"Add Session"**

**Session Types:**
- Regular classes
- Extra help sessions
- Exam review
- Project discussions
- Parent meetings

### 5.3 Deleting a Session from Timetable

**Access:**
1. Open side drawer
2. Select **"Delete Session from Timetable"** (DeleteSessionFromTimetable.html)

**Steps:**
1. View list of upcoming sessions
2. Select session to delete
3. Click **"Delete"**
4. Confirm deletion

**Notes:**
- Students will no longer see deleted sessions
- Delete recurring sessions individually or as a series
- Past sessions are archived automatically

### 5.4 Timetable Best Practices

- **Plan ahead:** Add sessions at least 24 hours in advance
- **Be consistent:** Use recurring sessions for regular classes
- **Update promptly:** Cancel or reschedule as soon as possible
- **Include details:** Add session descriptions for clarity
- **Share with students:** Students can view timetable from their dashboard

---

## 6. Notes & Homework Management

### 6.1 Understanding Note Types

**Two types of content:**

1. **Notes (Green Badge):**
   - Shared teaching materials
   - Visible to all students in the classroom
   - Lecture notes, study guides, reference materials

2. **Homework (Yellow Badge):**
   - Student submissions
   - Private to each student
   - You can see all homework, students see only their own

### 6.2 Uploading Notes/Materials

**Access:**
1. Open side drawer
2. Select **"Upload Notes"** (UploadNotes.html)

**Upload Process:**
1. Select **target classroom**
2. Click **"Choose File"**
3. Select file from computer (PDF, DOC, PPT, images, etc.)
4. **Optional:** Add description/title
5. Click **"Upload"**
6. Wait for upload confirmation

**File automatically tagged as:**
- **"note"** when uploaded by tutor
- Visible to all classroom students

**Supported File Types:**
- PDF documents
- Word documents (.doc, .docx)
- PowerPoint presentations (.ppt, .pptx)
- Images (JPG, PNG)
- Text files

### 6.3 Viewing Uploaded Notes

**Access:** LoadNotesAdmin.html

**View includes:**
- All notes from all classrooms
- All homework submissions from students
- File name and type
- Upload date and time
- Tag indicator (NOTE or HOMEWORK badge)
- Uploader email address

**Features:**
- Click to download/view file
- Sort by date or classroom
- Filter by type (notes vs homework)
- Delete files if needed

### 6.4 Managing Student Homework

**Homework Submission Flow (Student Side):**
1. Student accesses classroom comments
2. Clicks **"Upload Homework"** button
3. Selects and uploads file
4. File tagged as "homework" with student's email

**Viewing Student Homework (Tutor Side):**
1. Access **LoadNotesAdmin.html**
2. Look for yellow **"HOMEWORK"** badges
3. See student email for each submission
4. Download to review

**Homework Privacy:**
- Students can only see their own homework
- You can see ALL homework from ALL students
- Students can see all shared "notes"

### 6.5 Notes Management Tips

- **Organize by topic:** Use clear file names (e.g., "Chapter3_Physics.pdf")
- **Upload in advance:** Give students time to download
- **Regular cleanup:** Remove outdated materials
- **Size consideration:** Large files may take longer to upload
- **Multiple formats:** Provide notes in different formats when possible

---

## 7. Communication Features

### 7.1 Classroom Comments

**Purpose:** Central communication hub for each classroom

**Access Classroom Comments:**
1. From dashboard, select a classroom
2. Click on comment/discussion icon
3. Opens **AddCommentToClassroom.html**

**Adding Comments:**
1. Type your message in the text area
2. Click **"Submit Comment"**
3. Comment appears in thread

**Comment Uses:**
- Announcements
- Assignment instructions
- Clarifications
- Motivational messages
- Deadline reminders

**Student Access:**
- Students view comments via **ClassroomCommentForStudent.html**
- Can see all tutor comments
- Can upload homework from this page

### 7.2 Student Feedback

**Access:** AddFeedbackToStudent.html via admin panel

**Providing Feedback:**
1. Select student
2. Select classroom context
3. Enter feedback text
4. Rate performance (if applicable)
5. Submit

**Feedback Types:**
- Performance feedback
- Behavioral observations
- Improvement suggestions
- Praise and encouragement
- Progress reports

**Student View:**
- Students see their feedback on StudentProfile.html
- Private to each student
- Historical feedback visible

### 7.3 Direct Communication

**WhatsApp Support:**
- Customer support available at: **+23057882383**
- For urgent issues
- Technical support
- Billing questions

**Email Communication:**
- Through the platform (future feature)
- Direct to student/parent email addresses

### 7.4 Communication Best Practices

- **Be professional:** Maintain appropriate tone
- **Be timely:** Respond to student queries quickly
- **Be clear:** Use simple, direct language
- **Be encouraging:** Provide constructive feedback
- **Document:** Keep records of important communications

---

## 8. Virtual Classroom & Online Classes

### 8.1 Setting Up Virtual Rooms

**During Classroom Creation:**
1. Add virtual room URLs in classroom setup
2. Enter one URL per line
3. Can add multiple rooms per classroom

**Supported Platforms:**
- Zoom
- Google Meet
- Microsoft Teams
- Any web-based conferencing tool

**Multiple Rooms:**
- Different rooms for different purposes
- Breakout sessions
- One-on-one consultations
- Group discussions

### 8.2 Joining a Virtual Class

**From Dashboard:**
1. Locate classroom card
2. Click **"Join VR"** button (if virtual rooms configured)
3. Modal opens with virtual room options
4. Select room to join
5. Opens in new window/iframe

**Virtual Class Modal Features:**
- Full-screen iframe for immersive experience
- Close button to return to dashboard
- Camera and microphone permissions requested

**Alternative Access:**
1. Click classroom card
2. View classroom details
3. Copy virtual room URL
4. Open in browser

### 8.3 Conducting Online Classes

**Before Class:**
- Test audio and video
- Prepare materials (share screen capability)
- Ensure stable internet connection
- Have backup plan ready

**During Class:**
- Share virtual room link with students
- Use platform's native features (whiteboard, chat, screen share)
- Record session if needed (check platform settings)
- Monitor student participation

**After Class:**
- Upload class notes/recordings
- Post summary in classroom comments
- Assign homework if applicable
- Schedule next session

### 8.4 Whiteboard Feature (Premium)

> **🌟 Premium Feature**

**Access:** Whiteboard.html

**Features:**
- Interactive drawing tool
- Real-time collaboration
- Save whiteboard sessions
- Share with students

**Use Cases:**
- Math problem solving
- Diagram explanations
- Brainstorming sessions
- Visual concept mapping

### 8.5 Online Class Best Practices

- **Start on time:** Respect students' schedules
- **Clear agenda:** Share what will be covered
- **Interactive:** Engage students with questions
- **Record:** For students who miss class
- **Follow up:** Post materials after class

---

## 9. Premium Features & Billing

### 9.1 Understanding Pricing Plans

**Basic Plan:**
- **Cost:** Rs 50 per student per month
- **Included Features:**
  - Unlimited classrooms
  - Student management
  - Notes upload/download
  - Classroom comments
  - Feedback system
  - Virtual classroom access

**Premium Plan:**
- **Cost:** Rs 100 per student per month
- **All Basic Features PLUS:**
  - ✅ Whiteboard access
  - ✅ Timetable management
  - ✅ Advanced scheduling
  - ✅ Session planning tools

### 9.2 Upgrading to Premium

**Process:**
1. Click **info button** in navbar
2. In the modal, find **"Premium Plan"** section
3. Click **"Upgrade to Premium"**
4. Review upgrade modal:
   - Rs 100/student/month
   - 30-day lock-in period
   - Features included
5. Click **"Confirm Upgrade"**
6. Page reloads with premium features unlocked

**Important Upgrade Notes:**
- ⏰ **30-day lock period** begins immediately
- 📅 Lock expires 30 days from activation
- 💰 Billing changes to Rs 100/student/month
- 🔓 All premium features unlock immediately
- 🔒 Cannot downgrade during lock period

### 9.3 Premium Feature Lock Mechanism

**Lock Period Details:**
- Prevents gaming the billing system
- Ensures fair usage of premium features
- Automatic enforcement

**What Happens During Lock:**
- Premium features remain active
- Cannot downgrade to basic plan
- Can schedule a downgrade for later

**Lock Expiry:**
- After 30 days, lock expires
- If downgrade was scheduled, it happens automatically
- Otherwise, premium continues

### 9.4 Scheduling a Downgrade

**If you want to downgrade but are in lock period:**

1. Access premium plan section
2. Click **"Request Downgrade"**
3. Modal shows:
   - Current lock expiry date
   - "Will downgrade on [date]" message
4. Click **"Confirm"**
5. **PENDING_DOWNGRADE** flag set to true

**What Happens:**
- Premium features continue until lock expires
- On lock expiry date, automatic downgrade occurs:
  - ❌ Whiteboard access removed
  - ❌ Timetable features locked
  - 💰 Billing reverts to Rs 50/student/month
  - ✅ All other features remain

### 9.5 Canceling a Pending Downgrade

**If you change your mind:**

1. Access premium plan section
2. See "Downgrade Pending" notice
3. Click **"Cancel Downgrade"**
4. Confirm cancellation
5. Downgrade request removed

**Result:**
- Premium continues after lock period
- No downgrade occurs
- Can request downgrade again anytime

### 9.6 Viewing Premium Status

**Dashboard Info Modal shows:**
- Current plan: "Basic Plan" or "Premium Plan"
- Billing rate: Rs 50 or Rs 100 per student/month
- **If Premium:**
  - Activation date (DD/MM/YY HH:mm)
  - Lock expiry date (DD/MM/YY HH:mm)
  - Days remaining in lock period
  - Pending downgrade status

### 9.7 Billing Calculation

**Formula:**
```
Monthly Bill = (Number of Students) × (Rate per Student)
```

**Examples:**

Basic Plan:
- 10 students × Rs 50 = Rs 500/month
- 25 students × Rs 50 = Rs 1,250/month

Premium Plan:
- 10 students × Rs 100 = Rs 1,000/month
- 25 students × Rs 100 = Rs 2,500/month

**Student Count:**
- Total across ALL your classrooms
- Updated automatically as you add/remove students

---

## 10. Profile Management

### 10.1 Viewing Your Profile

**Access:**
- Click profile icon in navbar
- Or access from side drawer

**Profile Information Displayed:**
- Full name
- Email address
- Registration date
- Account status (Basic/Premium)
- Contact information
- Profile picture (if uploaded)

### 10.2 Editing Profile Information

**Access:** Edit Profile modal

**Steps:**
1. Click profile icon
2. Select **"Edit Profile"**
3. Modify fields:
   - Name
   - Contact number
   - Additional details
4. Click **"Save Changes"**
5. Confirmation message appears

**Cannot Edit:**
- Email address (used for login)
- Registration date
- Account type

### 10.3 Uploading Profile Picture

**Process:**
1. Access profile section
2. Click **"Upload Profile Picture"** or camera icon
3. Click **"Choose File"**
4. Select image from computer
5. Preview appears
6. Click **"Upload"**
7. Wait for upload confirmation

**Image Requirements:**
- Format: JPG, PNG, GIF
- Recommended size: 500x500 pixels
- Maximum file size: 5MB (typical)
- Square format works best

**Profile Picture Uses:**
- Appears in navbar
- Shows in student view
- Professional appearance
- Personal branding

### 10.4 Changing Password

**Security Best Practices:**
- Use strong, unique passwords
- Change periodically (every 3-6 months)
- Don't share credentials
- Logout on shared devices

**Password Change Process:**
1. Access profile settings
2. Enter current password
3. Enter new password
4. Confirm new password
5. Save changes

---

## 11. Student Attendance Tracking

### 11.1 Accessing Attendance System

**From Side Drawer:**
1. Open side drawer
2. Select **"Student Attendance"** (StudentAttendance.html)

### 11.2 Marking Attendance

**Process:**
1. Select classroom
2. Select date
3. View student list
4. Mark each student:
   - ✅ Present
   - ❌ Absent
   - 🔶 Late
   - 📝 Excused
5. Save attendance record

**Daily Workflow:**
- Mark attendance at start of each session
- Update if students arrive late
- Add notes for absences if needed

### 11.3 Viewing Attendance Reports

**Reports Available:**
- Daily attendance
- Weekly summary
- Monthly overview
- Individual student records

**Report Uses:**
- Track student participation
- Identify patterns
- Parent communication
- Administrative records

### 11.4 Attendance Best Practices

- **Mark promptly:** Record at session start
- **Be accurate:** Double-check before saving
- **Document:** Add notes for unusual absences
- **Review regularly:** Check for patterns
- **Communicate:** Inform parents of frequent absences

---

## 12. Troubleshooting & FAQs

### 12.1 Common Issues & Solutions

#### **Issue: Cannot Login**

**Possible Causes:**
- Incorrect credentials
- Account pending approval
- Browser cache issues

**Solutions:**
1. Verify email and password
2. Check for approval status message
3. Clear browser cache and cookies
4. Try different browser
5. Contact support if persists

#### **Issue: Virtual Room Not Opening**

**Solutions:**
1. Check that virtual room URL is correct
2. Ensure URL includes https://
3. Test URL in separate browser tab
4. Check popup blocker settings
5. Try different virtual room from list

#### **Issue: File Upload Fails**

**Possible Causes:**
- File too large
- Internet connection unstable
- Unsupported file type

**Solutions:**
1. Check file size (try smaller files)
2. Verify internet connection
3. Use supported formats (PDF, DOC, JPG, PNG)
4. Try uploading from different browser
5. Compress large files before uploading

#### **Issue: Students Not Seeing Notes**

**Check:**
1. Correct classroom selected during upload
2. File uploaded successfully (check LoadNotesAdmin.html)
3. Student enrolled in correct classroom
4. File tagged as "note" not "homework"

#### **Issue: Premium Features Not Unlocking**

**Solutions:**
1. Verify upgrade was confirmed
2. Refresh page (Ctrl+F5 or Cmd+R)
3. Check premium status in dashboard info modal
4. Logout and login again
5. Contact support if issue persists

#### **Issue: Timetable Not Displaying**

**Check:**
1. Premium plan is active
2. Sessions have been added
3. Correct date range selected
4. Page fully loaded

### 12.2 Frequently Asked Questions

#### **Q: How many classrooms can I create?**
A: Unlimited on both Basic and Premium plans.

#### **Q: Can students see each other's homework?**
A: No, homework submissions are private. Students only see their own homework and shared notes.

#### **Q: What happens to my data if I downgrade?**
A: All data is retained. You only lose access to premium features (whiteboard, timetable). Your classrooms, students, and notes remain intact.

#### **Q: Can I upgrade and downgrade multiple times?**
A: Yes, but each upgrade triggers a new 30-day lock period.

#### **Q: How do I add multiple virtual rooms?**
A: When creating/editing a classroom, enter one URL per line in the virtual rooms field.

#### **Q: Can I delete uploaded notes?**
A: Yes, access LoadNotesAdmin.html and delete as needed.

#### **Q: How do parents view their child's progress?**
A: Students can share their StudentProfile.html view which shows feedback and grades. Future versions may include parent portal.

#### **Q: Is there a mobile app?**
A: Currently web-based only, but responsive design works on mobile browsers.

#### **Q: How do I backup my data?**
A: All data is stored in Firebase. Contact support for backup options or export features.

#### **Q: Can I co-teach with another tutor?**
A: Not directly, but you can share virtual room links. Future updates may include co-teaching features.

### 12.3 Getting Help

#### **Customer Support**

**WhatsApp:** +23057882383
- Available for urgent issues
- Technical support
- Billing inquiries

**Access in Platform:**
1. Click info button in navbar
2. Scroll to customer support section
3. Click WhatsApp link

#### **Self-Help Resources**

- This user manual
- Test pages for feature verification
- Documentation index (DOCUMENTATION_INDEX.md)
- Feature-specific guides

#### **Best Practices for Support Requests**

When contacting support:
- Describe the issue clearly
- Include error messages (screenshot if possible)
- Mention browser and device type
- List steps taken to resolve
- Provide account email (for identification)

### 12.4 System Requirements

**Browser Requirements:**
- **Recommended:** Chrome, Firefox, Safari (latest versions)
- JavaScript enabled
- Cookies enabled
- Popup blocker disabled for virtual rooms

**Internet Connection:**
- Minimum: 2 Mbps for basic features
- Recommended: 5+ Mbps for video calls
- Stable connection for file uploads

**Device Compatibility:**
- Desktop/Laptop: Full functionality
- Tablet: Most features (some layout limitations)
- Mobile: Basic features (use desktop for best experience)

**Screen Resolution:**
- Minimum: 1024x768
- Recommended: 1366x768 or higher

---

## Quick Reference Card

### Daily Tasks Checklist

- [ ] Login and check dashboard
- [ ] Review new student enrollments
- [ ] Mark attendance for today's sessions
- [ ] Check classroom comments
- [ ] Upload any new notes/materials
- [ ] Review submitted homework
- [ ] Update timetable (if changes needed)
- [ ] Provide feedback to students
- [ ] Respond to messages

### Weekly Tasks

- [ ] Review attendance patterns
- [ ] Upload week's materials in advance
- [ ] Clean up old/outdated notes
- [ ] Check premium plan status
- [ ] Review student progress
- [ ] Plan next week's sessions
- [ ] Update timetable for coming week

### Monthly Tasks

- [ ] Review billing and student count
- [ ] Evaluate premium plan needs
- [ ] Backup important data
- [ ] Update profile information
- [ ] Review and archive old classrooms
- [ ] Analyze attendance trends
- [ ] Plan curriculum for next month

### Keyboard Shortcuts

- **ESC** - Close modals
- **Ctrl/Cmd + R** - Refresh page
- **Ctrl/Cmd + F** - Search within page

### Important Links (Within Platform)

- Dashboard: `DashboardAdmin.html`
- Upload Notes: `UploadNotes.html`
- View Notes: `LoadNotesAdmin.html`
- Attendance: `StudentAttendance.html`
- Timetable: `MyTimeTable.html` (Premium)
- Whiteboard: `Whiteboard.html` (Premium)

---

## Appendix

### A. Feature Access Matrix

| Feature | Basic Plan | Premium Plan |
|---------|:----------:|:------------:|
| Classrooms (Unlimited) | ✅ | ✅ |
| Student Management | ✅ | ✅ |
| Notes Upload/Download | ✅ | ✅ |
| Classroom Comments | ✅ | ✅ |
| Student Feedback | ✅ | ✅ |
| Virtual Classroom | ✅ | ✅ |
| Attendance Tracking | ✅ | ✅ |
| Profile Management | ✅ | ✅ |
| **Timetable Management** | ❌ | ✅ |
| **Whiteboard Access** | ❌ | ✅ |
| **Advanced Scheduling** | ❌ | ✅ |

### B. Glossary

- **Classroom:** A virtual space containing a group of students
- **Virtual Room:** Online meeting space URL (Zoom, Meet, etc.)
- **Note:** Teaching material shared with all students
- **Homework:** Student submission visible only to tutor and submitter
- **Session:** Scheduled class on timetable
- **Lock Period:** 30-day minimum subscription for premium features
- **Pending Downgrade:** Scheduled downgrade when lock expires
- **Admin/Tutor:** Interchangeable terms for teacher accounts

### C. Version History

**Version 1.0 (January 2026)**
- Initial comprehensive user manual
- Covers all existing features
- Includes premium features documentation
- Troubleshooting section added

---

## Support & Feedback

We continuously improve House of Tutors based on user feedback. If you have suggestions, feature requests, or encounter issues not covered in this manual:

**Contact:** +23057882383 (WhatsApp)

**Documentation Feedback:**
- Report unclear sections
- Suggest additional topics
- Request more examples

---

**End of User Manual**

*This manual covers all features available as of January 2026. Features and processes may be updated. Check for the latest version regularly.*

---

## Document Information

**Document Type:** User Manual  
**Target Audience:** Tutors/Administrators  
**Platform:** House of Tutors Web Application  
**Scope:** Complete daily usage guide  
**Format:** Markdown  
**Maintenance:** Update with each major feature release  

**Related Documentation:**
- `DOCUMENTATION_INDEX.md` - Index of all documentation
- `HOMEWORK_FEATURE_DOCUMENTATION.md` - Detailed homework feature docs
- `PREMIUM_FEATURES_IMPLEMENTATION.md` - Technical premium features docs
- `ADMIN_APPROVAL_IMPLEMENTATION.md` - Approval system documentation
- `README_LOGGING_FEATURE.md` - Admin logging feature

---

**Thank you for using House of Tutors!**

*Empowering education through technology*
