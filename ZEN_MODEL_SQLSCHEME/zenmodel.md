### TABLE CREATING

### create course table
```sql
CREATE TABLE Course (
    CourseID INT PRIMARY KEY,
    CourseName VARCHAR(255),
    Description TEXT,
    Duration INT
);
```

### create Instructor  table
```sql
CREATE TABLE Instructor (
    InstructorID INT PRIMARY KEY,
    FirstName VARCHAR(255),
    LastName VARCHAR(255),
    Email VARCHAR(255),
    Phone VARCHAR(15)
);
```
### create Student  table
```sql
CREATE TABLE Student (
    StudentID INT PRIMARY KEY,
    FirstName VARCHAR(255),
    LastName VARCHAR(255),
    Email VARCHAR(255),
    Phone VARCHAR(15)
);
```

### create Class  table
```sql
CREATE TABLE Class (
    ClassID INT PRIMARY KEY,
    CourseID INT,
    InstructorID INT,
    Schedule VARCHAR(255),
    Room VARCHAR(255),
    FOREIGN KEY (CourseID) REFERENCES Course(CourseID),
    FOREIGN KEY (InstructorID) REFERENCES Instructor(InstructorID)
);
```

### create Enrollment  table
```sql
CREATE TABLE Enrollment (
    EnrollmentID INT PRIMARY KEY,
    StudentID INT,
    ClassID INT,
    FOREIGN KEY (StudentID) REFERENCES Student(StudentID),
    FOREIGN KEY (ClassID) REFERENCES Class(ClassID)
);
```

### JOINS

### USING INNER JOIN FOR Class Tables and Course Tables
```sql
SELECT *
FROM Class
INNER JOIN Course ON Class.CourseID = Course.CourseID;
```

### USING LEFT JOIN FOR   Student Tables and Enrollment Tables
```sql
SELECT *
FROM Student
LEFT JOIN Enrollment ON Student.StudentID = Enrollment.StudentID;
```

### fetch  all records and fields  in course table 
```sql
SELECT * FROM Course;
```

### fetch all records and fields  in instructors table
```sql
SELECT * FROM Instructor;
```

### fetch all records and fields  in students table
```sql

SELECT * FROM Student;
```
### fetch all records and fields  in class table
```sql
SELECT * FROM Class;
```


### UPDATE

### Update course records
```sql
UPDATE Course
SET CourseName = 'New Course Name', Description = 'New Description', Duration = 10
WHERE CourseID = 1;
```

### Update instructor records
```sql
UPDATE Instructor
SET FirstName = 'New First Name', LastName = 'New Last Name', Email = 'newemail@example.com', Phone = '123-456-7890'
WHERE InstructorID = 1;
```

### Update student records:
```sql
UPDATE Student
SET FirstName = 'New First Name', LastName = 'New Last Name', Email = 'newemail@example.com', Phone = '123-456-7890'
WHERE StudentID = 1;
```

### Update class records:
```sql
UPDATE Class
SET Schedule = 'New Schedule', Room = 'New Room'
WHERE ClassID = 1;
```

### DELETE
### Delete a course
```sql
DELETE FROM Course
WHERE CourseID = 1;
```
### Delete an instructor 
```sql
DELETE FROM Instructor
WHERE InstructorID = 1;
```
### Delete a student 
```sql
DELETE FROM Student
WHERE StudentID = 1;
```
### Delete a class:
```sql
DELETE FROM Class
WHERE ClassID = 1;
```