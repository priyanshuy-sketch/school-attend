# College Faculty Management System

A comprehensive web-based faculty management system for tracking courses, students, and attendance with weekly report generation and PDF download functionality.

## Features

### 🔐 Faculty Authentication
- Secure login with email and password
- Session management with automatic logout
- Demo credentials provided for testing

### 📚 Course Management
- View assigned courses with detailed information
- Display registered students for each course
- Course details including schedule, credits, and description

### 📝 Attendance Tracking
- Easy-to-use attendance interface
- Bulk selection (select all/deselect all)
- Individual student marking (present/absent)
- Date-based attendance recording
- Mutual exclusivity between present/absent options
- **Persistent storage using localStorage** - attendance data is automatically saved
- **Automatic updates** - if attendance is taken twice for the same date, it updates the existing record

### 📊 Weekly Reports
- Generate comprehensive attendance reports
- Week-based or custom date range selection
- Daily breakdown with attendance statistics
- Summary statistics (total classes, students, attendance percentage)
- Detailed attendance records table
- **Real-time data reflection** - automatically displays attendance taken from the course details page

### 📄 PDF Export
- Download reports as PDF files
- Professional formatting with college branding
- Includes all report data and statistics

## File Structure

```
college-h/
├── database/
│   ├── faculty.json          # Faculty login credentials and details
│   ├── courses.json          # Course information and assignments
│   ├── students.json         # Student information
│   └── attendance.json       # Attendance records
├── faculty-index.html        # Landing page
├── faculty-login.html        # Login page
├── faculty-dashboard.html    # Main dashboard
├── course-details.html       # Course management page
├── weekly-report.html        # Report generation page
└── README.md                 # This file
```

## Database Structure

### Faculty Data (`database/faculty.json`)
```json
{
  "id": 1,
  "name": "Dr. Sarah Johnson",
  "email": "sarah.johnson@college.edu",
  "password": "faculty123",
  "department": "Computer Science",
  "phone": "+1-555-0101",
  "office": "CS-101",
  "courses": [1, 2]
}
```

### Course Data (`database/courses.json`)
```json
{
  "id": 1,
  "name": "Data Structures and Algorithms",
  "code": "CS-301",
  "description": "Advanced data structures and algorithmic problem solving",
  "credits": 3,
  "semester": "Fall 2024",
  "schedule": "Mon, Wed, Fri 10:00 AM - 11:00 AM",
  "faculty_id": 1,
  "students": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
}
```

### Student Data (`database/students.json`)
```json
{
  "id": 1,
  "name": "John Smith",
  "email": "john.smith@student.edu",
  "roll_number": "CS2024001",
  "year": 3,
  "department": "Computer Science"
}
```

### Attendance Data (Stored in Browser localStorage)
**Note:** Attendance records are stored in the browser's localStorage, not in `database/attendance.json`. This allows the data to persist across sessions without needing a backend server.

```json
{
  "id": 1234567890,
  "course_id": 1,
  "course_name": "Data Structures and Algorithms",
  "course_code": "CS-301",
  "faculty_id": 1,
  "faculty_name": "Dr. Sarah Johnson",
  "date": "2024-01-15",
  "students": [
    {
      "student_id": 1,
      "student_name": "John Smith",
      "roll_number": "CS2024001",
      "status": "present"
    }
  ],
  "created_at": "2024-01-15T10:30:00.000Z"
}
```

**How it works:**
1. When you take attendance on the course details page, the data is saved to `localStorage` under the key `attendanceData`
2. The weekly report page reads from the same `localStorage` to display attendance records
3. Data persists even after closing the browser
4. If you take attendance for the same course and date again, it updates the existing record

## Demo Credentials

For testing purposes, use these credentials:

1. **Dr. Sarah Johnson**
   - Email: `sarah.johnson@college.edu`
   - Password: `faculty123`
   - Courses: Data Structures and Algorithms, Quantum Mechanics

2. **Prof. Michael Chen**
   - Email: `michael.chen@college.edu`
   - Password: `faculty123`
   - Courses: Calculus III, Quantum Mechanics

3. **Dr. Emily Rodriguez**
   - Email: `emily.rodriguez@college.edu`
   - Password: `faculty123`
   - Courses: Data Structures and Algorithms, Calculus III

## Getting Started

1. **Open the system**: Navigate to `faculty-index.html` in your web browser
2. **Login**: Click "Faculty Login" and use one of the demo credentials
3. **Explore Dashboard**: View your assigned courses and faculty information
4. **Manage Courses**: Click on any course to view students and take attendance
5. **Take Attendance**: Use the attendance modal to mark student presence
6. **Generate Reports**: Access weekly reports with PDF download functionality

## Technical Features

### Frontend
- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Modern UI**: Clean, professional interface with smooth animations
- **Form Validation**: Client-side validation for all forms
- **Modal Windows**: Interactive attendance taking and report viewing

### Data Management
- **JSON Database**: Easy-to-edit JSON files for static data (courses, students, faculty)
- **localStorage**: Persistent storage for attendance records across browser sessions
- **Session Storage**: Secure client-side session management for login state
- **Real-time Updates**: Dynamic content loading and updates

### PDF Generation
- **HTML to PDF**: Converts report HTML to downloadable PDF
- **Professional Formatting**: Includes headers, statistics, and detailed tables
- **Multi-page Support**: Handles long reports with automatic pagination

## Customization

### Adding Faculty
Edit `database/faculty.json` to add new faculty members:
```json
{
  "id": 4,
  "name": "New Faculty Name",
  "email": "new.faculty@college.edu",
  "password": "newpassword",
  "department": "Department Name",
  "phone": "+1-555-0104",
  "office": "OFF-101",
  "courses": [1, 2, 3]
}
```

### Adding Courses
Edit `database/courses.json` to add new courses:
```json
{
  "id": 4,
  "name": "New Course Name",
  "code": "NEW-301",
  "description": "Course description",
  "credits": 3,
  "semester": "Fall 2024",
  "schedule": "Mon, Wed 2:00 PM - 3:00 PM",
  "faculty_id": 1,
  "students": [1, 2, 3]
}
```

### Adding Students
Edit `database/students.json` to add new students and update course student lists in `courses.json`.

## Browser Compatibility

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## Security Notes

- This is a demo system with client-side authentication
- In production, implement server-side authentication and data validation
- Use HTTPS for secure data transmission
- Implement proper password hashing and session management

## Future Enhancements

- Server-side backend with database integration
- Email notifications for attendance reports
- Advanced analytics and charts
- Mobile app development
- Integration with college management systems
- Role-based access control
- Automated report scheduling

## Support

For questions or issues with the system, please contact the development team or refer to the inline documentation in the HTML files.
# school-attend
