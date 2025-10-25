# UI Display Description

## Modal Appearance

When an admin accesses the `/info` endpoint, a modal appears with the following characteristics:

### Visual Design
- **Position**: Fixed at top-center of the viewport
- **Size**: Minimum 350px wide, auto height
- **Styling**: 
  - White background
  - Purple border (2px solid, purple-600)
  - Rounded corners
  - Shadow (shadow-lg)
  - z-index: 50 (appears above all other content)

### Content Structure

```
┌─────────────────────────────────────────┐
│                                         │
│      Admin Dashboard Info               │
│                                         │
│  ─────────────────────────────────────  │
│  Classrooms:                    4       │
│  ─────────────────────────────────────  │
│  Students:                      3       │
│  ─────────────────────────────────────  │
│  Last Loaded:    10/10/2025, 6:25:17 PM │
│  ─────────────────────────────────────  │
│                                         │
│          ┌───────────┐                  │
│          │   Close   │                  │
│          └───────────┘                  │
│                                         │
└─────────────────────────────────────────┘
```

### Typography & Colors
- **Heading**: 
  - "Admin Dashboard Info"
  - 2xl size
  - Bold
  - Purple-800 color

- **Labels** (left side):
  - "Classrooms:", "Students:", "Last Loaded:"
  - Semi-bold
  - Gray-700 color

- **Values** (right side):
  - Numbers and timestamp
  - Bold
  - Purple-700 color
  - Timestamp in smaller font

- **Close Button**:
  - Full width
  - Primary button styling (DaisyUI)
  - Top margin for spacing

### Responsive Behavior
- Centers horizontally on all screen sizes
- Adjusts top position to 20px from top of viewport
- Minimum width maintained at 350px
- On mobile: Maintains readability with proper spacing

### User Interaction
1. Modal appears automatically when /info endpoint is accessed
2. Information is displayed clearly with proper spacing
3. Close button removes the modal from DOM
4. No background overlay (intentional for simplicity)
5. Can continue using dashboard after closing modal

### Accessibility Features
- Semantic HTML structure
- Clear visual hierarchy
- Readable font sizes
- Good color contrast
- Keyboard accessible (button can be focused/clicked)

## Example Screenshots

### Desktop View (1920x1080)
```
Background: Dashboard with classroom cards

                    [Modal appears centered]
```

### Tablet View (768x1024)
```
Background: Dashboard (responsive layout)

              [Modal appears centered]
```

### Mobile View (375x667)
```
Background: Dashboard (mobile layout)

          [Modal appears centered]
         [Full width on small screens]
```

## Integration with Dashboard

The modal appears **over** the existing dashboard content:
- Dashboard background (with wallpaper) remains visible
- Classroom cards are visible behind the modal
- Navigation bar remains visible
- Drawer menu can still be accessed

This non-blocking design allows users to:
1. View the information
2. Close the modal
3. Continue using the dashboard normally

## Color Scheme

Following the existing DaisyUI theme and purple accent colors from the dashboard:

- **Primary Purple**: `#4c1d95` (used in dashboard cards hover)
- **Purple-600**: Border color
- **Purple-700**: Value text color
- **Purple-800**: Heading color
- **Gray-700**: Label text color
- **White**: Background

This maintains consistency with the existing House of Tutors branding and UI design.
