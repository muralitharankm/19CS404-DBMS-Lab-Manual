# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**

<img width="1371" height="274" alt="image" src="https://github.com/user-attachments/assets/041a2f1f-d870-4403-9f29-df2a9ed01cea" />


```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';

```

**Output:**

<img width="1148" height="332" alt="image" src="https://github.com/user-attachments/assets/284686f9-be9f-40ff-b74a-68fd6cc90cf3" />


**Question 2**

<img width="1334" height="459" alt="image" src="https://github.com/user-attachments/assets/85d0c1aa-9b5a-4d8c-81a5-1db63777fbd2" />


```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';

```

**Output:**

<img width="989" height="332" alt="image" src="https://github.com/user-attachments/assets/bf5479f0-a1c0-4c4a-9d49-7e7804d3abd2" />


**Question 3**

<img width="1070" height="659" alt="image" src="https://github.com/user-attachments/assets/802a2969-6b9c-41dd-9794-a28dfa930d84" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**

<img width="1084" height="673" alt="image" src="https://github.com/user-attachments/assets/ca2cf302-f3fd-4c9d-8e86-e546e098bc5b" />


**Question 4**

<img width="957" height="598" alt="image" src="https://github.com/user-attachments/assets/58af89dc-7486-44de-9b2a-6ff2a6f24e60" />


```sql
SELECT s.name AS "Salesman",
       c.cust_name,
       s.city
FROM salesman s
INNER JOIN customer c ON s.city = c.city;

```

**Output:**

<img width="912" height="525" alt="image" src="https://github.com/user-attachments/assets/4e3eae75-9752-4d4a-b3a2-47ebcb3aaf39" />


**Question 5**

<img width="1323" height="490" alt="image" src="https://github.com/user-attachments/assets/820b1602-abc4-4401-bbbc-ec118cb42040" />


```sql
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NULL;


```

**Output:**

<img width="814" height="375" alt="image" src="https://github.com/user-attachments/assets/ebe3e987-a612-4fbc-88a5-9cab7fbccc0e" />


**Question 6**

<img width="1257" height="619" alt="image" src="https://github.com/user-attachments/assets/8500576b-c2ce-4995-a21f-40eab1ea2cda" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;

```

**Output:**

<img width="1071" height="580" alt="image" src="https://github.com/user-attachments/assets/35d12d73-622c-4839-90f5-01e5072a1749" />


**Question 7**

<img width="1171" height="341" alt="image" src="https://github.com/user-attachments/assets/23e50e89-c839-4c89-a63d-578194b2066b" />


```sql
SELECT p.*
FROM patients p
INNER JOIN appointments a ON p.patient_id = a.patient_id
WHERE a.appointment_date BETWEEN '2024-02-01' AND '2024-02-28';

```

**Output:**

<img width="1132" height="254" alt="image" src="https://github.com/user-attachments/assets/b0752ba7-9c2b-45e7-bc3a-5b05d6567d89" />


**Question 8**

<img width="1255" height="322" alt="image" src="https://github.com/user-attachments/assets/9c768247-4191-4e46-8bb1-cfe7972ed694" />


```sql
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id;

```

**Output:**

<img width="791" height="652" alt="image" src="https://github.com/user-attachments/assets/a23d8028-173b-43bd-8f6d-58ac825e334c" />


**Question 9**

<img width="1046" height="476" alt="image" src="https://github.com/user-attachments/assets/1b958b1b-59d6-4361-b42f-20df80fbbb65" />


```sql
SELECT 
    c.cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.grade < 300
ORDER BY c.customer_id ASC;

```

**Output:**

<img width="930" height="432" alt="image" src="https://github.com/user-attachments/assets/3470859a-8296-4ff6-9854-b16c711872aa" />


**Question 10**

<img width="1270" height="441" alt="image" src="https://github.com/user-attachments/assets/55ac578e-a077-47e6-9904-f2f965736b9e" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.city AS "city",
    s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;

```

**Output:**

<img width="960" height="364" alt="image" src="https://github.com/user-attachments/assets/254d8932-def8-4392-8f4b-fe7ed976a5b5" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
