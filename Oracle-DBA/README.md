
# 🗄️ Oracle DBA | SQL, Database Design & Stored Procedures

## 📌 1. Overview

This module documents **Oracle Database Administration (DBA)** and SQL assignments completed during the **Cognizant CIS Multicloud technical capstone training program**.

The assignments focused on relational database design, database normalization, SQL table creation, primary and foreign key relationships, and stored procedure fundamentals.

Two case studies were covered:

1. **Student–Course Enrollment System:** Designing a normalized relational database using five related tables.
2. **Employee Bonus Calculation:** Exploring a stored procedure that calculates employee bonuses based on job designation.

The module combines database design principles, SQL execution exercises, and result verification.

## 🛠️ 2. Technologies & Concepts Covered

| Technology / Concept | Purpose | Training Coverage |
|---|---|---|
| Oracle Database | Relational database management | Database fundamentals |
| SQL | Database definition and data manipulation | Table creation and query execution |
| PL/SQL | Oracle procedural SQL programming | Stored procedure fundamentals |
| Database Normalization | Organizing relational data | 1NF, 2NF, and 3NF |
| Primary Keys | Uniquely identifying records | Database design |
| Foreign Keys | Establishing relationships between tables | Relational modeling |
| Database Constraints | Supporting data integrity | Conceptual and design coverage |
| Stored Procedures | Reusable database-side logic | Employee bonus case study |

## 🎯 3. Technical Objectives

- Understand relational database architecture.
- Identify entities and relationships from business requirements.
- Design tables for a Student–Course Enrollment System.
- Apply database normalization principles.
- Understand primary key and foreign key relationships.
- Explore SQL table creation and data manipulation.
- Understand PL/SQL stored procedure fundamentals.
- Apply conditional business logic to employee bonus calculations.
- Review SQL execution results.
- Strengthen foundational database administration and troubleshooting knowledge.

---

## 🏗️ 4. Assignment 1 — Database Normalization & Table Creation

### 4.1 Case Study: Student–Course Enrollment System

**Objective:** Design a relational database to manage students, courses, teachers, departments, and course enrollments.

### 4.2 Business Requirements

The assignment defined three requirements:

1. A student can enroll in multiple courses.
2. Each course is taught by a teacher.
3. Each teacher belongs to a department.

These requirements form the basis for identifying database entities and their relationships.

### 4.3 Entity Identification

The database design contains five tables.

| Table | Purpose |
|---|---|
| `STUDENT` | Stores student information |
| `COURSE` | Stores course information |
| `TEACHER` | Stores teacher details |
| `DEPARTMENT` | Stores department information |
| `ENROLLMENT` | Connects students with their enrolled courses |

### 4.4 Relational Database Structure

The following diagram illustrates the conceptual relationships described in the assignment.

```text
           DEPARTMENT
                |
                | Has Teachers
                v
             TEACHER
                |
                | Teaches
                v
              COURSE
                |
                | Has Enrollments
                v
            ENROLLMENT
                ^
                | Enrolls In
                |
              STUDENT
```

The `ENROLLMENT` table represents the association between students and courses.

This approach supports students enrolling in multiple courses without storing repeated course details in the student table.

### 4.5 Database Normalization

Normalization organizes relational data to reduce unnecessary duplication and improve data consistency.

The assignment covered three normalization levels.

#### First Normal Form (1NF)

**Objective:** Organize data into tables containing atomic values.

Key concepts:

- Each column contains a single value per row.
- Repeating groups are avoided.
- Related entities are represented in appropriate tables.

**Application to the Case Study:**

Student, course, teacher, and department information are separated into distinct tables.

#### Second Normal Form (2NF)

**Objective:** Eliminate partial functional dependencies.

Key concepts:

- The table must satisfy 1NF.
- Non-key attributes must depend on the complete candidate key.
- Attributes depending on only part of a composite key should be moved to an appropriate table.

**Application to the Case Study:**

Course details belong in the `COURSE` table rather than being repeated as attributes dependent only on `Course_ID` within an enrollment relationship.

#### Third Normal Form (3NF)

**Objective:** Eliminate inappropriate transitive dependencies.

Key concepts:

- The table must satisfy 2NF.
- Non-key attributes should not depend transitively on a candidate key through another non-key attribute.
- Related information should be organized into appropriate entities.

**Application to the Case Study:**

Department information is maintained in the `DEPARTMENT` table rather than repeatedly storing department details with teacher records.

### 4.6 Primary Key & Foreign Key Concepts

The assignment covered relational keys used to identify records and establish relationships.

| Key Type | Purpose | Example |
|---|---|---|
| Primary Key (PK) | Uniquely identifies a table record | `Student_ID` |
| Foreign Key (FK) | References a key in a related table | `Course_ID` in `ENROLLMENT` |

**Primary Keys**

A primary key uniquely identifies each record and does not permit null values.

**Foreign Keys**

A foreign key establishes a relationship between tables and helps enforce referential integrity when implemented as a database constraint.

### 4.7 SQL Table Creation

The assignment documented SQL execution for creating the five relational tables:

```text
STUDENT
COURSE
TEACHER
DEPARTMENT
ENROLLMENT
```

**Documented Result:**

The capstone report includes a screenshot of SQL table creation output.

The screenshot provides evidence of the table creation exercise.

The report does not provide enough textual detail to independently verify every column definition or implemented constraint, so the table relationships above describe the documented design.

### Technical Outcome

Designed a five-entity relational database model, studied 1NF–3NF normalization, explored primary and foreign key relationships, and documented SQL table creation.

---

## ⚙️ 5. Assignment 2 — Stored Procedure for Employee Bonus Calculation

### 5.1 Case Study: Employee Bonus Calculation

**Objective:** Create a stored procedure to calculate employee bonuses based on designation.

The assignment introduced reusable database-side business logic using SQL and stored procedure concepts.

### 5.2 Employee Data Structure

The case study used employee information containing:

| Field | Purpose |
|---|---|
| Employee ID | Identifies an employee |
| Employee Name | Stores the employee's name |
| Designation | Identifies the employee's job role |
| Salary | Stores the salary amount |
| Bonus | Stores the calculated bonus amount |

### 5.3 Sample Data

The assignment covered inserting employee records for testing the bonus calculation.

The documented results include employees with different designations and salary values.

### 5.4 Stored Procedure Fundamentals

A stored procedure is a named program unit stored in a database and executed when required.

In Oracle Database, stored procedures can be written using PL/SQL.

**Benefits Studied:**

- Reuse of database-side logic.
- Reduced repetition of SQL operations.
- Centralized implementation of business rules.
- Easier maintenance of recurring database operations.
- Ability to manage execution permissions.

Performance improvements depend on the procedure design and workload; stored procedures are not automatically faster in every situation.

### 5.5 Bonus Calculation Logic

The assignment specified a bonus rule for Managers.

**Documented Rule:**

```text
Designation: Manager
Bonus Rate: 20% of Salary
```

**Formula:**

```text
Bonus = Salary × Bonus Rate
```

**Manager Example:**

```text
Salary = 50,000
Bonus Rate = 20%

Bonus = 50,000 × 0.20
Bonus = 10,000
```

The report notes that other designations may use different percentages, but does not explicitly specify those rules.

### 5.6 Stored Procedure Workflow

The assignment described the following workflow:

1. Create an employee table.
2. Insert sample employee records.
3. Define a stored procedure.
4. Read employee data.
5. Determine the applicable bonus using designation-based logic.
6. Calculate the bonus.
7. Update the employee records.
8. Retrieve the results for verification.

**Conceptual Processing Flow:**

```text
         Employee Records
                 |
                 v
        Stored Procedure
                 |
                 v
        Read Designation
                 |
                 v
       Apply Bonus Logic
                 |
                 v
        Calculate Bonus
                 |
                 v
       Update Employee Data
                 |
                 v
       Retrieve SQL Results
```

This diagram represents the documented procedure logic rather than the exact PL/SQL source code.

### 5.7 Documented Execution Results

The supplied assignment summary includes these sample results:

| Employee | Designation | Salary | Bonus |
|---|---|---:|---:|
| John | Manager | 50,000 | 10,000 |
| Arun | Developer | 40,000 | 4,000 |
| Kavin | Manager | 60,000 | 12,000 |
| Priya | Tester | 35,000 | 3,500 |

**Result Interpretation:**

- John's bonus is 20% of 50,000.
- Kavin's bonus is 20% of 60,000.
- The Developer and Tester results are shown as documented examples.
- The exact procedure rules for non-manager designations are not specified in the source report.

### 5.8 Verification

The capstone includes a screenshot documenting the stored procedure execution result.

The result illustrates designation-based bonus calculations and retrieval of employee records.

### Technical Outcome

Explored PL/SQL stored procedure concepts, conditional bonus calculations, database updates, and SQL result verification.

---

## ✅ 6. Verification & Technical Results

| Assignment | Technical Activity | Supporting Evidence |
|---|---|---|
| Database Design | Identified five related entities | Capstone documentation |
| Normalization | Studied 1NF, 2NF, and 3NF | Design explanation |
| SQL Table Creation | Created relational tables | SQL execution screenshot |
| Database Keys | Reviewed primary and foreign key relationships | Assignment documentation |
| Employee Bonus | Defined designation-based calculation logic | Stored procedure case study |
| Procedure Execution | Reviewed calculated bonus results | Execution screenshot |

The documented assignments demonstrate foundational database design and SQL execution knowledge.

---

## 📸 7. Supporting Evidence

### 7.1 SQL Table Creation — Student–Course Enrollment System

The screenshot documents SQL table creation output for the five-entity relational database model.

**Tables Covered:**

- `STUDENT`
- `COURSE`
- `TEACHER`
- `DEPARTMENT`
- `ENROLLMENT`

![SQL Table Creation](Screenshots/SQL-Table-Creation.png)

### 7.2 Stored Procedure — Employee Bonus Calculation

The screenshot documents the stored procedure exercise and its employee bonus calculation results.

The case study demonstrates the use of designation-based business logic in database operations.

![Stored Procedure Execution](Screenshots/Stored-Procedure-Execution.png)

---

## 🧠 8. Key Learning Outcomes

- Understood relational database design fundamentals.
- Identified entities from business requirements.
- Designed a Student–Course Enrollment data model.
- Studied normalization through 1NF, 2NF, and 3NF.
- Understood primary and foreign key relationships.
- Explored SQL table creation and execution.
- Learned how database constraints support data integrity.
- Understood Oracle PL/SQL stored procedure fundamentals.
- Explored designation-based employee bonus calculations.
- Reviewed database updates and query results.
- Strengthened foundational SQL and database administration knowledge.

---

## 🚀 9. Lab Summary

This Oracle DBA capstone covered relational database design, normalization, SQL table creation, and stored procedure fundamentals.

The **Student–Course Enrollment System** assignment introduced relational modeling using five tables and normalization principles to organize data.

The **Employee Bonus Calculation** assignment introduced reusable database-side logic and designation-based calculations through stored procedure concepts.

The supporting screenshots document selected SQL execution and verification activities completed during Cognizant CIS Multicloud technical training.

These exercises strengthened foundational database skills relevant to **SQL development, application support, database administration, cloud infrastructure, and DevOps engineering**.
