# Homework Submission Feature - Visual Guide

## UI Changes Overview

### 1. Student Classroom Comment Page (ClassroomCommentForStudent.html)

#### Before
```
+--------------------------------------------------+
|                 Add a Comment                     |
+--------------------------------------------------+
| Your Comment                                      |
| [Text area for comment]                          |
|                                                   |
| [Submit Comment - Full Width Purple Button]      |
+--------------------------------------------------+
```

#### After
```
+--------------------------------------------------+
|                 Add a Comment                     |
+--------------------------------------------------+
| Your Comment                                      |
| [Text area for comment]                          |
|                                                   |
| [Submit Comment]     [Upload Homework]           |
| Purple Button (50%)  Blue Button (50%)           |
+--------------------------------------------------+
```

**Changes:**
- Added "Upload Homework" button (blue color)
- Both buttons now share horizontal space (flex layout)
- Each button takes 50% width with gap between them

### 2. Upload Notes Page (UploadNotes.html)

#### Behavior Changes

**When accessed by Admin/Tutor (normal flow):**
- Back button → DashboardAdmin.html
- Uploaded notes tagged as "note"
- UploaderEmail set to admin email

**When accessed by Student (via Upload Homework button):**
- Back button → ClassroomCommentForStudent.html
- Uploaded files tagged as "homework"
- UploaderEmail set to student email

**New Data Structure:**
```javascript
{
  Name: "filename.pdf",
  ID: 123,
  Link: "https://...",
  Time: 1766416726112,
  Tag: "homework",              // NEW: "homework" or "note"
  UploaderEmail: "student@email.com"  // NEW: tracks uploader
}
```

### 3. Student Notes View (LoadNotes.html)

#### Display Changes

**Before:**
```
+--------------------------------------------------+
|            Uploaded Notes                         |
+--------------------------------------------------+
| [Icon] Filename.pdf                              |
|        Uploaded on: 01/01/2025, 10:30:00        |
+--------------------------------------------------+
| [Icon] Document.docx                             |
|        Uploaded on: 02/01/2025, 14:20:00        |
+--------------------------------------------------+
```

**After:**
```
+--------------------------------------------------+
|            Uploaded Notes                         |
+--------------------------------------------------+
| [Icon] Filename.pdf                              |
|        Uploaded on: 01/01/2025, 10:30:00        |
|        [NOTE]  (green badge)                     |
+--------------------------------------------------+
| [Icon] My_Homework.docx                          |
|        Uploaded on: 02/01/2025, 14:20:00        |
|        [HOMEWORK]  (yellow badge)                |
+--------------------------------------------------+
```

**Filtering Logic:**
- ✓ Shows all notes with "note" tag (green badge)
- ✓ Shows only own homework (yellow badge)
- ✗ Hides homework from other students

### 4. Admin Notes View (LoadNotesAdmin.html)

#### Display Changes

**Before:**
```
+--------------------------------------------------+
|            Uploaded Notes                         |
+--------------------------------------------------+
| [Icon] Filename.pdf                     [Delete] |
|        Uploaded on: 01/01/2025, 10:30:00        |
+--------------------------------------------------+
```

**After:**
```
+--------------------------------------------------+
|            Uploaded Notes                         |
+--------------------------------------------------+
| [Icon] Filename.pdf                     [Delete] |
|        Uploaded on: 01/01/2025, 10:30:00        |
|        [NOTE] (green badge)                      |
|        Uploaded by: teacher@email.com            |
+--------------------------------------------------+
| [Icon] Student_HW.docx                  [Delete] |
|        Uploaded on: 02/01/2025, 14:20:00        |
|        [HOMEWORK] (yellow badge)                 |
|        Uploaded by: student@email.com            |
+--------------------------------------------------+
```

**Admin View Features:**
- ✓ Sees all notes and homework from all students
- ✓ Tag badges show type (NOTE/HOMEWORK)
- ✓ Uploader email identifies who submitted each item
- ✓ Delete button available for all items

## Color Scheme

### Buttons
- **Submit Comment**: Purple (#7E3AF2)
- **Upload Homework**: Blue (#1E40AF)

### Tag Badges
- **NOTE Badge**: 
  - Background: Green (#28a745)
  - Text: White
  - Label: "NOTE"

- **HOMEWORK Badge**:
  - Background: Yellow (#ffc107)
  - Text: Black
  - Label: "HOMEWORK"

### Text
- **Uploader Email**: Gray (#666), Italic, 0.85em font size

## User Flow Diagrams

### Student Homework Submission Flow
```
┌─────────────────────────┐
│  Classroom Comments     │
│  [Upload Homework]      │
└────────┬────────────────┘
         │ Click
         ▼
┌─────────────────────────┐
│  Upload Notes Page      │
│  (Student Mode)         │
│  - Select File          │
│  - Upload               │
└────────┬────────────────┘
         │ Upload Complete
         ▼
┌─────────────────────────┐
│  Back to Comments       │
│  (Auto redirect)        │
└────────┬────────────────┘
         │ View
         ▼
┌─────────────────────────┐
│  Load Notes (Student)   │
│  - See own homework     │
│  - See shared notes     │
└─────────────────────────┘
```

### Admin Viewing Flow
```
┌─────────────────────────┐
│  Admin Dashboard        │
│  [View Notes]           │
└────────┬────────────────┘
         │ Click
         ▼
┌─────────────────────────┐
│  Load Notes (Admin)     │
│  - All notes visible    │
│  - All homework visible │
│  - Uploader emails      │
│  - Tag badges           │
│  - Delete buttons       │
└─────────────────────────┘
```

## Responsive Design

### Desktop View
- Buttons: Full text visible, comfortable sizing
- Tag badges: Full size (0.85em font)
- Icons: 200x200px

### Mobile View
- Buttons: Adapt to smaller screens, maintain horizontal layout
- Tag badges: Slightly smaller but readable
- Icons: 100x100px
- All elements stack vertically when needed

## Accessibility Features

- **Color Contrast**: Tag badges have sufficient contrast ratios
- **Button Labels**: Clear, descriptive text
- **Focus States**: Buttons have visible focus rings
- **Keyboard Navigation**: All interactive elements keyboard accessible

## Browser Compatibility

Tested and compatible with:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Notes

- Uses Tailwind CSS for styling consistency
- Bootstrap components for buttons and modals
- Font Awesome icons for visual elements
- Native Toast library for notifications
