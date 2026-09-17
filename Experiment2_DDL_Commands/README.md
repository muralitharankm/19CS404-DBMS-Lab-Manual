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
### 2. ALTER
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
Create a table named Department with the following constraints:
DepartmentID as INTEGER should be the primary key.
DepartmentName as TEXT should be unique and not NULL.
Location as TEXT.

<img width="828" height="117" alt="image" src="https://github.com/user-attachments/assets/791590c7-2570-468f-9207-31ec5d4acee9" />


```sql
create table Department(
DepartmentID INTEGER primary key ,
DepartmentName text UNIQUE not null  ,
Location text);
```

**Output:**

<img width="1368" height="157" alt="image" src="https://github.com/user-attachments/assets/3ae56c70-9fff-4fc7-91b1-82cdb2b4ff21" />


**Question 2**
---
Insert the following employees into the Employee table:

EmployeeID  Name        Position    Department  Salary
----------  ----------  ----------  ----------  ----------
2           John Smith  Developer   IT          75000
3           Anna Bell   Designer    Marketing   68000


<img width="475" height="127" alt="image" src="https://github.com/user-attachments/assets/74fd23ba-e876-4b5f-adfd-fb91acf01948" />


```sql
insert into Employee(EmployeeID,Name,Position,Department,Salary) values(2,'John Smith','Developer','IT',75000);
insert into Employee(EmployeeID,Name,Position,Department,Salary) values(3,'Anna Bell','Designer',"Marketing",68000);
```
**Output:**

<img width="1166" height="204" alt="image" src="https://github.com/user-attachments/assets/125cd11f-dba8-47db-9073-c5098321e265" />


**Question 3**
---
Insert a new product with ProductID 101, Name Laptop, Category Electronics, Price 1500, and Stock 50 into the Products table.

<img width="603" height="121" alt="image" src="https://github.com/user-attachments/assets/120ab450-ec85-488e-9510-d63e4d8b39fc" />


```sql
insert into Products(ProductID,Name,Category,Price,Stock)values(101,'Laptop','Electronics',1500,50);

```

**Output:**

<img width="1089" height="132" alt="image" src="https://github.com/user-attachments/assets/8fc72705-d81e-44cc-8b63-264cf21e4108" />

**Question 4**
---
Create a table named Orders with the following columns:

OrderID as INTEGER
OrderDate as TEXT
CustomerID as INTEGER

<img width="552" height="151" alt="image" src="https://github.com/user-attachments/assets/6ddbd3e6-6211-4648-ab57-99127ec88df1" />


```sql
create table Orders(
OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER);
```

**Output:**

<img width="1112" height="227" alt="image" src="https://github.com/user-attachments/assets/d74b2164-1844-4ab4-b010-8459b540d334" />


**Question 5**
---
Write a SQL Query  to change the name of attribute "name" to "first_name"  and add mobilenumber as number ,DOB as Date in the table Companies. 

 For example:

Test	Result
pragma table_info('Companies');
cid         name        type        notnull     dflt_value  pk
----------  ----------  ----------  ----------  ----------  ----------
0           id          int         0                       0
1           first_name  varchar(50  0                       0
2           address     text        0                       0
3           email       varchar(50  0                       0
4           phone       varchar(10  0                       0
5           mobilenumb  number      0                       0
6           DOB         Date        0                       0

```sql
alter table Companies rename column name to first_name;
alter table Companies add column mobilenumber number;
alter table Companies add column DOB Date;
```

**Output:**
<img width="1073" height="199" alt="image" src="https://github.com/user-attachments/assets/6f5b3950-8505-4421-a874-9969f350213d" />



**Question 6**
---
Create a table named Reviews with the following columns:

ReviewID as INTEGER
ProductID as INTEGER
Rating as REAL
ReviewText as TEXT
For example:

Test	Result
pragma table_info('Reviews');
cid         name        type        notnull     dflt_value  pk
----------  ----------  ----------  ----------  ----------  ----------
0           ReviewID    INTEGER     0                       0
1           ProductID   INTEGER     0                       0
2           Rating      REAL        0                       0
3           ReviewText  TEXT        0                       0


```sql
create table Reviews(
ReviewID  INTEGER,
ProductID  INTEGER,
Rating  REAL,
ReviewText  TEXT);
```

**Output:**

<img width="1191" height="212" alt="image" src="https://github.com/user-attachments/assets/0a88dd08-ee25-416b-a963-70f2fd39c125" />


**Question 7**
---
Write an SQL query to add two new columns, designation and net_salary, to the table Companies. The designation column should have a data type of varchar(50), and the net_salary column should have a data type of number.

 For example:

Test	Result
pragma table_info('Companies');
cid         name        type        notnull     dflt_value  pk
----------  ----------  ----------  ----------  ----------  ----------
0           id          int         0                       0
1           name        varchar(50  0                       0
2           address     text        0                       0
3           email       varchar(50  0                       0
4           phone       varchar(10  0                       0
5           designatio  varchar(50  0                       0
6           net_salary  number      0                       0


```sql
alter table Companies add column designation varchar(50);
alter table Companies add column net_salary number;
```

**Output:**

<img width="1073" height="199" alt="image" src="https://github.com/user-attachments/assets/c67cd7b8-cf72-4ef5-9acc-21dd210ba566" />


**Question 8**
---
Create a table named Employees with the following columns:

EmployeeID as INTEGER
FirstName as TEXT
LastName as TEXT
HireDate as DATE
For example:

Test	Result
pragma table_info('Employees');
cid   name        type        notnull     dflt_value  pk
----  ----------  ----------  ----------  ----------  ----------
0     EmployeeID  INTEGER     0                       0
1     FirstName   TEXT        0                       0
2     LastName    TEXT        0                       0
3     HireDate    DATE        0                       0
```sql
create table Employees(
EmployeeID INTEGER,
FirstName TEXT,
LastName TEXT,
HireDate DATE);
```

**Output:**

<img width="1009" height="183" alt="image" src="https://github.com/user-attachments/assets/f095c0b7-fed0-4914-bde6-b9f1f2788cf9" />


**Question 9**
---
Insert all customers from Old_customers into Customers

Table attributes are CustomerID, Name, Address, Email

For example:

Test	Result
select * from Customers;
CustomerID  Name             Address         Email
----------  ---------------  --------------  ---------------------
301         Michael Johnson  123 Elm Street  michael.j@example.com
302         Sarah Lee        456 Oak Avenue  sarah.lee@example.com
303         David Wilson     789 Pine Road   david.w@example.com


```sql
insert into Customers select* from old_customers;
```

**Output:**

<img width="1007" height="156" alt="image" src="https://github.com/user-attachments/assets/716ef1dc-937e-4606-9afc-2ab1368b07d5" />


**Question 10**
---
Create a table named Products with the following constraints:
ProductID as INTEGER should be the primary key.
ProductName as TEXT should be unique and not NULL.
Price as REAL should be greater than 0.
StockQuantity as INTEGER should be non-negative.
For example:

Test	Result
INSERT INTO Products (ProductID, ProductName, Price, StockQuantity) VALUES (1, 'Laptop', 999.99, 10);
select * from Products;
ProductID   ProductName  Price       StockQuantity
----------  -----------  ----------  -------------
1           Laptop       999.99      10


```sql
Create table Products(

ProductID INTEGER primary key,
ProductName TEXT unique not NULL,
Price REAL check(Price>0),
StockQuantity INTEGER check (StockQuantity>=0)
);

```

**Output:**

<img width="1188" height="148" alt="image" src="https://github.com/user-attachments/assets/65e6c4a3-5adb-4d8c-815d-599b3e6e6394" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
