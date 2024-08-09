# Timetable-Management-System
This project is a part of the Final Project submission for Software Tools Laboratory(PCCCS492)
This is a simple GUI-based Timetable Management System built using Python's Tkinter library. The system allows different types of users (Students, Faculty, Admin) to log in view, modify and update  their respective timetables.

## Features
- **User Authentication**: Users can log in as a Student, Faculty, or Admin.
- **Password Visibility Toggle**: Users can toggle between showing and hiding their password input.
- **Role-Based Access**: 
  - Students can view their section-wise timetable.
  - Faculty members can view their course-specific timetable.
  - Admins have full control and can manage the system.

## Prerequisites
- Python 3.x
- Tkinter (usually comes pre-installed with Python)
- SQLite3 (for the database)
- The following Python modules: `os`, `sys`, `sqlite3`

## Folder Structure

```
├── windows/
│   ├── timetable_stud.py       # Handles student timetable interface
│   ├── timetable_fac.py        # Handles faculty timetable interface
│   ├── admin_screen.py         # Handles admin functionalities
├── files/
│   ├── timetable.db            # SQLite database containing user and timetable data
├── main.py                     # Main script to launch the application
└── README.md                   # This file
```

##  Run : 
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/ns7523/Timetable-Management-System.git
   cd Timetable-Management-System
   ```
2. **Launch the Application**:
   ```zsh
   python main.py
   ```
3. **Ensure Dependencies are Met**:
   - Python 3.x should be installed.
   - The required libraries (`tkinter`, `sqlite3`) should be installed. Typically, they are included in the Python standard library.
     
4. **Login as Different Users**:
   - **Student**: Use a valid Student ID and password.
   - **Faculty**: Use a valid Faculty ID and password.
   - **Admin**: Use `admin` as both the username and password.

---

## Database Structure
- **FACULTY Table**:
  ```bash
  CREATE TABLE FACULTY  (
    FID CHAR(10) NOT NULL PRIMARY KEY,
    PASSW CHAR(50) NOT NULL,
    NAME CHAR(50) NOT NULL,
    INI CHAR(5) NOT NULL,
    EMAIL CHAR(50) NOT NULL,
    SUBCODE1 char(10) NOT NULL,
    SUBCODE2 char(10)  );
  
- **SCHEDULE Table**:
  ```bash
  CREATE TABLE SCHEDULE  (
    ID CHAR(10) NOT NULL,
    DAYID INT NOT NULL,
    PERIODID INT NOT NULL,
    SUBCODE CHAR(10) NOT NULL,
    SECTION CHAR(5) NOT NULL,
    FINI CHAR(5) NOT NULL  );
  
- **STUDENT Table**:
  ```bash
  CREATE TABLE STUDENT  (
    SID CHAR(10) NOT NULL PRIMARY KEY,
    PASSW CHAR(50) NOT NULL,
    NAME CHAR(50) NOT NULL,
    ROLL CHAR(5) NOT NULL,
    SECTION CHAR(5) NOT NULL  );
  
- **SUBJECTS Table**:
  ```bash
  CREATE TABLE SUBJECTS (
    SUBCODE CHAR(10) NOT NULL PRIMARY KEY,
    SUBNAME CHAR(50) NOT NULL,
    SUBTYPE CHAR(1) NOT NULL  );

- **sqlite_sequence**:
  ``` bash
  CREATE TABLE sqlite_sequence(name,seq)  ;

## Future Improvements
- Add more robust error handling.
- Implement a more secure password storage mechanism.
- Expand admin functionalities for managing users and timetables.
- Add the ability to update and delete records.

