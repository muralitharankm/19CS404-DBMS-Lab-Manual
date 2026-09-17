# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**

<img width="1026" height="542" alt="image" src="https://github.com/user-attachments/assets/ac74916a-4b24-440e-ba06-22e592f8def5" />


```sql
SELECT ord_no, purch_amt, ord_date, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE commission = (SELECT MAX(commission) FROM salesman)
);

```

**Output:**

<img width="904" height="380" alt="image" src="https://github.com/user-attachments/assets/f9827809-93a7-44d3-9218-5cce7a0def3b" />


**Question 2**

<img width="1042" height="547" alt="image" src="https://github.com/user-attachments/assets/4ba78418-29d7-432e-9f6a-b09be2e1f927" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE city = 'New York'
);

```

**Output:**

<img width="917" height="374" alt="image" src="https://github.com/user-attachments/assets/80108e64-271c-45b2-9293-22fbd247eef1" />


**Question 3**

<img width="1022" height="495" alt="image" src="https://github.com/user-attachments/assets/7c0077e0-d29e-4f00-8cb1-e8f1ec550178" />


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';

```

**Output:**

<img width="986" height="319" alt="image" src="https://github.com/user-attachments/assets/b168b94a-684b-4ef1-b145-2cc4322723ee" />


**Question 4**

<img width="871" height="375" alt="image" src="https://github.com/user-attachments/assets/85ae9949-1f82-4a26-9fc0-6350fe752944" />


```sql
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="814" height="369" alt="image" src="https://github.com/user-attachments/assets/01d121c8-4c0c-4ad8-97bc-567bae9e36b4" />


**Question 5**

<img width="1082" height="527" alt="image" src="https://github.com/user-attachments/assets/320edb97-4fe6-4a86-873e-48bb94487eac" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE city = 'New York'
);

```

**Output:**

<img width="980" height="386" alt="image" src="https://github.com/user-attachments/assets/dbe8a604-d8bd-4865-8bf1-2e0660e087e4" />


**Question 6**

<img width="768" height="432" alt="image" src="https://github.com/user-attachments/assets/4932fc47-a91f-4a2d-b268-11a34c519cbf" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;

```

**Output:**

<img width="963" height="291" alt="image" src="https://github.com/user-attachments/assets/307243e5-cd23-4e83-9517-f6f7caaf765f" />


**Question 7**

<img width="1012" height="437" alt="image" src="https://github.com/user-attachments/assets/7077250e-f6f1-4047-84d0-ea3cc886942d" />


```sql
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**

<img width="692" height="356" alt="image" src="https://github.com/user-attachments/assets/15339c76-8dcf-4311-bf01-c865a2dec662" />


**Question 8**

<img width="971" height="429" alt="image" src="https://github.com/user-attachments/assets/ca23a0a1-aea3-455f-9e26-62d047914ce1" />


```sql
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MIN(grade)
    FROM GRADES
    WHERE subject = g.subject
);


```

**Output:**

<img width="774" height="353" alt="image" src="https://github.com/user-attachments/assets/8f59b741-ba9f-4b8d-aa8d-dafa7f4cb96a" />


**Question 9**

<img width="863" height="364" alt="image" src="https://github.com/user-attachments/assets/93de25b8-a2ef-46af-b3c4-45ef49e1bf53" />


```sql
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);

```

**Output:**

<img width="1134" height="386" alt="image" src="https://github.com/user-attachments/assets/2c7a4a7d-15a6-4b72-bd19-3a28f88c231c" />


**Question 10**

<img width="1210" height="378" alt="image" src="https://github.com/user-attachments/assets/4b639dad-b862-4a59-ac2e-f66dbd9bb971" />


```sql
SELECT *
FROM orders
WHERE salesman_id IN (
    SELECT DISTINCT salesman_id
    FROM orders
    WHERE customer_id = 3007
);

```

**Output:**

<img width="1038" height="353" alt="image" src="https://github.com/user-attachments/assets/5b13c8c7-d45f-44e8-b32b-88e7e4837ddf" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
