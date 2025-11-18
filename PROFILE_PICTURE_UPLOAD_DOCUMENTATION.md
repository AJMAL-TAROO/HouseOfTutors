# Profile Picture Upload Feature Documentation

## Overview
This document describes the profile picture upload feature added to the admin edit profile functionality in the House of Tutors platform.

## Feature Description
Administrators can now upload and update their profile pictures through the Edit Profile modal. The feature provides:
- Visual profile picture preview
- File selection and validation
- Upload progress tracking
- Integration with Firebase Storage
- Persistent storage of profile picture URL in Firebase Realtime Database

## Implementation Details

### Location
- **File**: `DashboardAdmin.html`
- **Modal**: Edit Profile Modal (lines 238-327)
- **JavaScript**: Lines 1398-1498

### User Interface Components

#### Profile Picture Section
Located at the top of the Edit Profile modal, the section includes:
1. **Profile Picture Preview**
   - 128x128px circular image
   - Purple border (4px)
   - Shadow effect
   - Default image: `img/user-icon.png`

2. **Change Profile Picture Button**
   - Camera icon overlay button
   - Positioned at bottom-right of profile picture
   - Primary color styling
   - Tooltip: "Change Profile Picture"

3. **File Input**
   - Hidden file input element
   - Accepts: JPEG, PNG, JPG, GIF, WebP
   - Maximum size: 5MB

4. **Upload Progress Indicator**
   - Progress bar (0-100%)
   - Text showing percentage
   - Hidden by default, shown during upload

### Technical Implementation

#### Firebase Integration
```javascript
// Storage Import
import { getStorage, ref as storageRef, uploadBytesResumable, getDownloadURL } 
  from "https://www.gstatic.com/firebasejs/11.1.0/firebase-storage.js";

// Storage Initialization
const storage = getStorage(app);
```

#### Storage Structure
- **Path**: `ADMIN_PROFILE_PICTURES/{filename}`
- **Filename Format**: `profile_{adminKey}_{timestamp}.{extension}`
- **Example**: `profile_ADMIN_001_1700253600000.jpg`

#### Database Structure
- **Field**: `PROFILE_PICTURE`
- **Type**: String (URL)
- **Location**: `ADMIN/{adminKey}/PROFILE_PICTURE`
- **Example**: `https://firebasestorage.googleapis.com/.../profile_ADMIN_001_1700253600000.jpg`

### Functions

#### `selectProfilePicture()`
Triggers the hidden file input to allow file selection.
```javascript
window.selectProfilePicture = function() {
    document.getElementById('profilePictureInput').click();
};
```

#### `previewProfilePicture(event)`
Handles file selection, validation, and preview display.

**Validations:**
1. File type must be: JPEG, PNG, JPG, GIF, or WebP
2. File size must be ≤ 5MB

**Process:**
1. Validates file type
2. Validates file size
3. Stores file reference
4. Displays preview using FileReader

#### `uploadProfilePicture()`
Uploads the selected file to Firebase Storage.

**Returns:** Promise<string> - Download URL of uploaded file

**Process:**
1. Creates unique filename
2. Creates storage reference
3. Shows progress bar
4. Uploads file using `uploadBytesResumable`
5. Tracks upload progress
6. Returns download URL on completion

#### Modified `loadEditProfileData()`
Loads existing profile picture when opening Edit Profile modal.

**Added Logic:**
```javascript
if (adminData.PROFILE_PICTURE) {
    document.getElementById('editProfilePicturePreview').src = adminData.PROFILE_PICTURE;
} else {
    document.getElementById('editProfilePicturePreview').src = 'img/user-icon.png';
}
```

#### Modified Form Submission
Updated to handle profile picture upload before saving profile data.

**Process:**
1. Upload profile picture if selected
2. Get download URL
3. Add URL to update data
4. Update admin record
5. Reset file input
6. Close modal and show success message

### Error Handling

#### File Validation Errors
- Invalid file type: Shows error message
- File too large: Shows error message
- Clears file input on validation failure

#### Upload Errors
- Network errors: Displays error message
- Permission errors: Displays error message
- Disables submit button during upload
- Re-enables submit button on error

### Security Considerations

1. **File Type Validation**: Only allows image file types
2. **File Size Validation**: Limits uploads to 5MB
3. **Client-side Validation**: Pre-upload checks
4. **Firebase Security Rules**: Should be configured server-side
5. **Unique Filenames**: Prevents file overwrites and conflicts

### User Experience

#### Upload Flow
1. User opens Edit Profile modal
2. User clicks camera icon button
3. File picker dialog opens
4. User selects image file
5. File is validated
6. Image preview updates immediately
7. User clicks "Save Changes"
8. Profile picture uploads (with progress bar)
9. Profile data saves with picture URL
10. Modal closes with success message

#### Visual Feedback
- Instant preview on file selection
- Progress bar during upload
- Error messages for validation failures
- Success message on completion

### Browser Compatibility
- Modern browsers supporting ES6 modules
- FileReader API support required
- Firebase SDK v11.1.0 compatibility

### Testing

#### Manual Testing Checklist
- [ ] File selection works
- [ ] Invalid file type is rejected
- [ ] Oversized file is rejected
- [ ] Valid file shows preview
- [ ] Upload progress displays correctly
- [ ] Upload completes successfully
- [ ] Profile picture URL saves to database
- [ ] Profile picture loads on modal reopen
- [ ] Error messages display correctly
- [ ] Form submission works with/without new picture

#### Test Page
A standalone test page is available: `test_profile_picture_upload.html`
- Demonstrates UI components
- Simulates upload progress
- Shows file validation

### Future Enhancements

Potential improvements:
1. Image cropping/editing before upload
2. Multiple image format conversions
3. Image compression for smaller file sizes
4. Drag-and-drop file upload
5. Profile picture gallery/history
6. Social media profile picture import
7. Avatar/placeholder generator

### Troubleshooting

#### Common Issues

**Profile picture doesn't display:**
- Check Firebase Storage URL is accessible
- Verify PROFILE_PICTURE field exists in database
- Check browser console for CORS errors

**Upload fails:**
- Verify Firebase Storage is initialized
- Check Firebase Storage rules allow writes
- Verify internet connection
- Check file meets validation requirements

**Progress bar doesn't appear:**
- Check uploadProgress element exists
- Verify CSS classes are correct
- Check browser console for JavaScript errors

### Support
For issues or questions, contact: ajtaroo@gmail.com
