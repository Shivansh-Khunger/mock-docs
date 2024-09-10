# Users

This document outlines the planned features and routes for upcoming versions of the Mockpad User Service.

## Version 1.0

### Admin

| Method | Endpoint                      | Description             | req.params          | req.body               | req.file     | Access Level | Checkbox |
| ------ | ----------------------------- | ----------------------- | ------------------- | ---------------------- | ------------ | ------------ | -------- |
| POST   | /admin/register               | Register a new admin    |                     | `{ adminDetails }`     |              | Protected    | [ ]      |
| POST   | /admin/login                  | Admin login             |                     | `{ adminCredentials }` |              | Public       | [ ]      |
| GET    | /admin/:adminId               | Get admin details       | `{ adminId }`       |                        |              | Private      | [ ]      |
| PUT    | /admin/:adminId               | Update admin details    | `{ adminId }`       | `{ updatedAdmin }`     |              | Private      | [ ]      |
| DELETE | /admin/:adminId               | Delete an admin         | `{ adminId }`       |                        |              | Private      | [ ]      |
|        |                               |                         |                     |                        |              |              |          |
| POST   | /admin/teacher/bulk           | Add teachers in bulk    |                     |                        | teachers.csv | Private      | [ ]      |
| POST   | /admin/teacher                | Add a single teacher    |                     | `{ teacherDetails }`   |              | Private      | [ ]      |
| PUT    | /admin/teacher/bulk           | Update teachers in bulk |                     | N/A                    |              | Private      | [ ]      |
| PUT    | /admin/teacher/:teacherId     | Update a single teacher | `{ teacherId }`     | `{ updatedTeacher }`   |              | Private      | [ ]      |
|        |                               |                         |                     |                        |              |              |          |
| POST   | /admin/student/bulk           | Add students in bulk    |                     |                        | students.csv | Private      | [ ]      |
| POST   | /admin/student                | Add a single student    |                     | `{ studentDetails }`   |              | Private      | [ ]      |
| PUT    | /admin/student/bulk           | Update students in bulk |                     | N/A                    |              | Private      | [ ]      |
| PUT    | /admin/student/:studentRollno | Update a single student | `{ studentRollno }` | `{ updatedStudent }`   |              | Private      | [ ]      |

### Teacher

| Method | Endpoint            | Description            | req.params      | req.body                 | req.file | Access Level        | Checkbox |
| ------ | ------------------- | ---------------------- | --------------- | ------------------------ | -------- | ------------------- | -------- |
| POST   | /teacher/login      | Teacher login          |                 | `{ teacherCredentials }` |          | Public              | [ ]      |
| GET    | /teacher/:teacherId | Get teacher details    | `{ teacherId }` |                          |          | Public              | [ ]      |
| PUT    | /teacher/:teacherId | Update teacher details | `{ teacherId }` | `{ updatedTeacher }`     |          | Public              | [ ]      |
| GET    | /teachers           | Get all teachers       |                 |                          |          | Public (Admin only) | [ ]      |

### Student

| Method | Endpoint                | Description            | req.params          | req.body                 | req.file | Access Level        | Checkbox |
| ------ | ----------------------- | ---------------------- | ------------------- | ------------------------ | -------- | ------------------- | -------- |
| POST   | /student/login          | Student login          |                     | `{ studentCredentials }` |          | Public              | [ ]      |
| GET    | /student/:studentRollno | Get student details    | `{ studentRollno }` |                          |          | Public              | [ ]      |
| PUT    | /student/:studentRollno | Update student details | `{ studentRollno }` | `{ updatedStudent }`     |          | Public              | [ ]      |
| GET    | /students               | Get all students       |                     |                          |          | Public (Admin only) | [ ]      |

### Explanation

- **Method**: HTTP method used for the route (e.g., GET, POST, PUT, DELETE).
- **Endpoint**: The URL path for the route.
- **Description**: A brief description of what the route does.
- **req.params**: The expected URL parameters (e.g., `{ adminId }`, `{ teacherId }`, `{ studentRollno }`).
- **req.body**: The expected structure of the request body (e.g., `{ adminDetails }`, `{ teacherCredentials }`, `{ updatedStudent }`).
- **req.file**: Indicates if a file is expected in the request (e.g., `teachers.csv`, `students.csv`).
- **Access Level**: Specifies if the route is public, protected, or private. If a route is public but intended for admin use only, it is noted as "Public (Admin only)".
- **Checkbox**: A placeholder for tracking the implementation status of the route.
