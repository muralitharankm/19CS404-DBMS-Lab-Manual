# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Write a SQL query to delete a doctor from Doctors table whos specialization is 'Cardiology'

Sample table: Doctors

attributes: doctor_id, first_name, last_name, specialization

```sql
delete from Doctors where specialization = 'Cardiology';
```

**Output:**

<img width="780" height="175" alt="image" src="https://github.com/user-attachments/assets/480d297a-7753-461e-8c87-8e51fb03f9fb" />


**Question 2**
---
<img width="704" height="289" alt="image" src="https://github.com/user-attachments/assets/825ba8a8-a1e5-4e7c-bdb1-54d83f198fcb" />


```sql
select* from EmployeeInfo1 where Department is null;
```

**Output:**

<img width="1084" height="145" alt="image" src="https://github.com/user-attachments/assets/34e8d852-ba11-401c-aa60-8b1230b7ee70" />


**Question 3**
---
Write a SQL statement to Increase the selling price by 10% for all products in the 'Bakery' category in the products table.

Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id

```sql
update Products  set sell_price= sell_price*1.10  where category = 'Bakery';
```

**Output:**

<img width="1092" height="312" alt="image" src="https://github.com/user-attachments/assets/a20ccfac-e8bf-4e53-b35d-ec875530a7ce" />


**Question 4**
---

Question text
Decrease the reorder level by 30 percent where the product name contains 'cream' and quantity in stock is higher than reorder level in the products table.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT
 

For example:

Test	Result
select changes();
changes()
----------
3


```sql
update PRODUCTS set reorder_lvl=reorder_lvl*0.70 where product_name like '%cream%' and quantity>reorder_lvl;
```

**Output:**

<img width="1106" height="234" alt="image" src="https://github.com/user-attachments/assets/3286928e-647a-492c-97f0-d692178038aa" />


**Question 5**
---
<img width="650" height="266" alt="image" src="https://github.com/user-attachments/assets/4b2e71b6-380d-499f-a5a7-401bfc780f77" />


```sql
select* from EmployeeInfo where EmpId between 5 and 9;
```

**Output:**

<img width="1097" height="129" alt="image" src="https://github.com/user-attachments/assets/750f6400-6f66-40ab-b237-4912a29aaafa" />


**Question 6**
---
Write a SQL query to reduce the reorder level by 30% where cost price is more than 50 and quantity in stock is less than 100 in the products table.

Products Table 

name          type       
----------    ---------- 
product_id     INT PRIMARY KEY        
product_name   VARCHAR(10) 
category       VARCHAR(50) 
cost_price     DECIMAL(10) 
sell_price     DECIMAL(10) 
reorder_lvl    INT        
quantity       INT        
supplier_id    INT               
For example:

Test	Result
--pragma table_info('products');
select changes();
changes()
----------
2


```sql
update Products set reorder_lvl=reorder_lvl*0.70 where cost_price>50 and quantity<100;
```

**Output:**

<img width="1088" height="257" alt="image" src="https://github.com/user-attachments/assets/2c6a0ecc-c9e8-425c-9638-392584ca33b1" />


**Question 7**
---
Write a SQL query to find all employees who were hired in the last 6 months from the emp table. 

Note: Assume current date as '01-09-2024'

emp table

cid         name        type        
----------  ----------  ---------- 
0           empno       INT         
1           ename       VARCHAR(100)
2           job         VARCHAR(50)
3           mgr         INT        
4           hiredate    DATE        
5           sal         DECIMAL(10,2)  
6           comm        DECIMAL(10,2)  
7           deptno      INT         
For example:

Result
empno       ename       job         mgr         hiredate    sal         comm        deptno
----------  ----------  ----------  ----------  ----------  ----------  ----------  ----------
7369        SMITH       CLERK       7902        2024-06-01  800                     20
7499        ALLEN       SALESMAN    7698        2024-06-01  1600        300         30
7521        WARD        SALESMAN    7698        2024-06-01  1250        500         30
7900        JAMES       CLERK       7698        2024-06-01  950                     30
7902        FORD        ANALYST     7566        2024-06-01  3000                    20
7934        MILLER      CLERK       7782        2024-06-01  1300                    10


```sql
select *from emp where hiredate>=('2024-03-01')and hiredate<=('2024-09-01');
```

**Output:**

<img width="1075" height="215" alt="image" src="https://github.com/user-attachments/assets/b7714f4d-f3ee-4672-ae0a-768fad839d3f" />


**Question 8**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_CITY' is not 'New York' and 'OUTSTANDING_AMT' is greater than 5000.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |
For example:

Test	Result
select changes();
changes()
----------
16


```sql
delete from Customer where CUST_CITY != 'New York' and OUTSTANDING_AMT>5000;
```

**Output:**

<img width="1062" height="313" alt="image" src="https://github.com/user-attachments/assets/9565ce6b-9d0c-4ea8-bcce-09650c0f1e37" />


**Question 9**
---
Write a SQL query to remove rows from the table 'customer' with the following condition -

1. 'cust_city' should begin with the letter 'L',

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |
For example:

Test	Result
SELECT * FROM customer WHERE cust_country='UK';
CUST_CODE   CUST_NAME   CUST_CITY   WORKING_AREA  CUST_COUNTRY  GRADE       OPENING_AMT  RECEIVE_AMT  PAYMENT_AMT  OUTSTANDING_AMT  PHONE_NO    AGENT_CODE
----------  ----------  ----------  ------------  ------------  ----------  -----------  -----------  -----------  ---------------  ----------  ----------
C00013      Holmes      London      London        UK            2           6000         5000         7000         4000             BBBBBBB     A003
C00024      Cook        London      London        UK            2           4000         9000         7000         6000             FSDDSDF     A006
C00015      Stuart      London      London        UK            1           6000         8000         3000         11000            GFSGERS     A003
C00023      Karl        London      London        UK            0           4000         6000         7000         3000             AAAABAA     A006
C00010      Charles     Hampshair   Hampshair     UK            3           6000         4000         5000         5000             MMMMMMM     A009
CUST_CODE   CUST_NAME   CUST_CITY   WORKING_AREA  CUST_COUNTRY  GRADE       OPENING_AMT  RECEIVE_AMT  PAYMENT_AMT  OUTSTANDING_AMT  PHONE_NO    AGENT_CODE
----------  ----------  ----------  ------------  ------------  ----------  -----------  -----------  -----------  ---------------  ----------  ----------
C00010      Charles     Hampshair   Hampshair     UK            3           6000         4000         5000         5000             MMMMMMM     A009

```sql
delete from Customer where cust_city like "L%";
```

**Output:**

<img width="1059" height="637" alt="image" src="https://github.com/user-attachments/assets/a1d2058d-ea68-48ca-8c66-e2b980633737" />

**Question 10**
---
Write a query to find the top 2 products with the highest discount percentage. Return product_id, original_price, discount_percentage, and discounted_price.

Sample table: Products

product_id | original_price | discount_percentage

-----------------------------------------------------------

"101" "50" "0.1"

"102" "150" "0.15"

"103" "200" "0.2"

"104" "300" "0.25"

 For example:

Result
product_id  original_price  discount_percentage  discounted_price
----------  --------------  -------------------  ----------------
104         300.0           0.25                 225.0
103         200.0           0.2                  160.0


```sql
select product_id, original_price, discount_percentage,original_price*(1- discount_percentage) as discounted_price from Products order by discount_percentage desc limit 2;
```

**Output:**

<img width="804" height="155" alt="image" src="https://github.com/user-attachments/assets/96cc6be0-7748-4a04-ace7-66a19d5fd8de" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
