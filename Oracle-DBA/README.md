
# Oracle DBA – SQL & Database Management

## Overview

This section documents Oracle Database and SQL capstone assignments completed during Cognizant CIS Multicloud training, focusing on relational database design, normalization, SQL table creation, and stored procedures.

## Technologies & Concepts Covered

- **Oracle Database:** Relational database fundamentals
- **SQL:** Table creation, data insertion, and data retrieval
- **PL/SQL:** Stored procedure fundamentals
- **Database Normalization:** First, Second, and Third Normal Forms (1NF, 2NF, 3NF)
- **Database Constraints:** Primary keys and foreign keys
- **Relational Data Modeling:** Table relationships and data integrity

## 1. Database Normalization & Table Creation

### Case Study: Student–Course Enrollment System

**Objective:** Design a relational database to manage student enrollment in courses.

### Requirements

- A student can enroll in multiple courses.
- Each course is taught by a teacher.
- Each teacher belongs to a department.

### Database Tables

Designed the following five related tables:

1. **STUDENT** – Stores student information.
2. **COURSE** – Stores course information.
3. **TEACHER** – Stores teacher details.
4. **DEPARTMENT** – Stores department information.
5. **ENROLLMENT** – Establishes the relationship between students and courses.

### Database Normalization

- **1NF:** Organized data into separate tables with atomic column values.
- **2NF:** Reviewed full functional dependency and elimination of partial dependencies.
- **3NF:** Reviewed elimination of transitive dependencies.

### Primary Key & Foreign Key Constraints

- Used primary keys to uniquely identify records.
- Covered foreign keys to establish relationships between tables.
- Studied how relational constraints support data integrity.

### Result

The capstone document includes SQL execution output confirming creation of the five tables.

## 2. Stored Procedures – Employee Bonus Calculation

### Case Study: Employee Bonus Calculation

**Objective:** Calculate employee bonuses based on their designation using a stored procedure.

### Employee Table

The case study uses employee records containing:

- Employee ID
- Employee Name
- Designation
- Salary
- Bonus

### Stored Procedure Logic

- Reviewed creation of a stored procedure for employee bonus calculation.
- Applied designation-based bonus calculation logic.
- Manager bonus: 20% of salary.
- Reviewed updating and retrieving employee bonus values.

### Execution Results

The documented output includes the following sample results:

| Employee | Designation | Salary | Bonus |
|----------|-------------|--------|-------|
| John | Manager | 50000 | 10000 |
| Arun | Developer | 40000 | 4000 |
| Kavin | Manager | 60000 | 12000 |
| Priya | Tester | 35000 | 3500 |

## Key Learning Areas

- Relational database design
- SQL table creation and data manipulation
- Database normalization (1NF, 2NF, 3NF)
- Primary key and foreign key relationships
- SQL constraints and data integrity
- Stored procedure fundamentals
- Designation-based bonus calculation
- Database query execution and result verification


## Evidence

The following screenshots document SQL execution results from the Oracle DBA capstone assignments.

### 1. SQL Table Creation – Student–Course Enrollment System

Created five relational database tables: STUDENT, COURSE, TEACHER, DEPARTMENT, and ENROLLMENT.

The execution output confirms successful table creation.

![SQL Table Creation](Screenshots/SQL-Table-Creation.png)

### 2. Stored Procedure – Employee Bonus Calculation

Reviewed the execution results of a designation-based employee bonus calculation.

The output displays employee records with their designations, salaries, and calculated bonuses.

![Stored Procedure Execution](Screenshots/Stored-Procedure-Execution.png)

---

## Skills Demonstrated

- Relational database design and normalization
- SQL table creation and execution
- Primary key and foreign key concepts
- SQL and PL/SQL stored procedure fundamentals
- Employee bonus calculation logic
- Database result verification

