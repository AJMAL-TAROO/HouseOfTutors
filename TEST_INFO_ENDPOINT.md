# Testing the /info Endpoint

## How to Test

1. Log in as an admin user at `LoginAdmin.html`
2. After successful login, you'll be redirected to `DashboardAdmin.html`
3. Manually change the URL in the browser to: `DashboardAdmin.html/info`
4. The page will:
   - Display a modal showing:
     - Number of classrooms assigned to the admin
     - Number of students assigned to the admin
     - Timestamp when the dashboard was loaded
   - Automatically log this information to Firebase Realtime Database under the `LOGS` node

## Firebase Database Structure

The logs are stored in Firebase under the `LOGS` node with the following structure:

```json
{
  "LOGS": {
    "LOG_UNIQUE_ID": {
      "ADMIN_EMAIL": "admin@example.com",
      "ADMIN_KEY": "ADMIN_1",
      "CLASSROOM_COUNT": 4,
      "STUDENT_COUNT": 3,
      "TIMESTAMP": 1234567890123,
      "DATE": "2025-10-10T18:25:17.473Z"
    }
  }
}
```

## Example Test Users

Based on the current_firebase_db.json:

1. **Admin 1**
   - Email: ajtaroo@gmail.com
   - Password: 585054
   - Expected Classrooms: 4 (1001, 1002, 1007, 1008)
   - Expected Students: 3

2. **Admin 2**
   - Email: house.of.tutors.48@gmail.com
   - Password: 890555
   - Expected Classrooms: 6 (1001, 1002, 1003, 1004, 1005, 1006)
   - Expected Students: 13

3. **Admin 3**
   - Email: yuveshramiad@gmail.com
   - Password: 453366
   - Expected Classrooms: 2 (1009, 1010)
   - Expected Students: 0

## Notes

- The logging happens automatically when the URL contains `/info`
- The information is displayed in a modal that can be closed by clicking the "Close" button
- Each access to the `/info` endpoint creates a new log entry in Firebase
- The timestamp is stored in both milliseconds (TIMESTAMP) and ISO format (DATE) for flexibility
