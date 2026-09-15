# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTERER Diagram Workshop – Submission Template
Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

Scenario A: City Fitness Club Management
Business Context:
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

Requirements:

Members register with name, membership type, and start date.
Each member can join multiple programs (Yoga, Zumba, Weight Training).
Trainers assigned to programs; a program may have multiple trainers.
Members may book personal training sessions with trainers.
Attendance recorded for each session.
Payments tracked for memberships and sessions.
ER Diagram:
Screenshot 2026-08-06 113454
Entities and Attributes
Entity	Attributes (PK, FK)	Notes
Member	MemberID (PK), Name, Phone, MembershipType	Stores member personal and membership details
Program	ProgramID (PK), Type, Duration	Different fitness programs (Yoga, Zumba,etc.)
Trainers	TrainerID (PK), Name, Phone, Specialization, Experience	Trainers working in the gym
PersonalTrainingSession	SessionID (PK), MemberID (FK), TrainerID (FK), Date, Time	Personal training session booked by members
Attendance	ID (PK), MemberID (FK), ProgramID (FK), Date, Status	Tracks which member attended which program
Payment	ID (PK), MemberID (FK), Amount, Date, Mode	Payment records of members
Relationships and Constraints
Relationship	Cardinality	Participation	Notes
Member–Program	M:N	Partial on both sides	Attendance links Members to Programs
Program–Trainers	M:N	Partial	Trainers may run multiple programs
Member–PersonalTrainingSession	1:M	Total on PTS side	Each session must belong to a member
Trainer–PersonalTrainingSession	1:M	Total on PTS side	Each session requires one trainer
Member–Attendance	1:M	Total on Attendance	Attendance entry refer to a member
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- Paste Question 1 here

```sql
-- Paste your SQL code below for Question 1
```

**Output:**

![Output1](output.png)

**Question 2**
---
-- Paste Question 2 here

```sql
-- Paste your SQL code below for Question 2
```

**Output:**

![Output2](output.png)

**Question 3**
---
-- Paste Question 3 here

```sql
-- Paste your SQL code below for Question 3
```

**Output:**

![Output3](output.png)

**Question 4**
---
-- Paste Question 4 here

```sql
-- Paste your SQL code below for Question 4
```

**Output:**

![Output4](output.png)

**Question 5**
---
-- Paste Question 5 here

```sql
-- Paste your SQL code below for Question 5
```

**Output:**

![Output5](output.png)

**Question 6**
---
-- Paste Question 6 here

```sql
-- Paste your SQL code below for Question 6
```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Paste Question 7 here

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
