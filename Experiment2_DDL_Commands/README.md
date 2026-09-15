# Experiment 2: DDL Commands
Test	Result
SELECT * FROM Books;
ISBN            Title                    Author      Publisher   Year
--------------  -----------------------  ----------  ----------  ----------
978-1234567890  Data Science Essentials  Jane Doe    TechBooks   2024

```sql
INSERT INTO Books (ISBN,Title,Author,Publisher,Year) VALUES ('978-1234567890','Data Science Essentials','Jane Doe','TechBooks',2024);
```

**Output:**

<img width="1481" height="617" alt="image" src="https://github.com/user-attachments/assets/6ebc9f5f-4f49-4130-a517-c3e190a01572" />



**Question 10**
---
Write a SQL Query for inserting the below values in the table Customers

ID               NAME             AGE  ADDRESS     SALARY      
---------------  ---------------  ---  ----------  ----------  
1                Ramesh           32   Ahmedabad   2000
2                Khilan           25   Delhi       1500
3                Kaushik          23   Kota        2000
 

For example:

Test	Result
SELECT * FROM Customers;
ID          NAME        AGE         ADDRESS     SALARY
----------  ----------  ----------  ----------  ----------
1           Ramesh      32          Ahmedabad   2000
2           Khilan      25          Delhi       1500
3           Kaushik     23          Kota        2000

```sql
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY) VALUES (1,'Ramesh',32,'Ahmedabad',2000);
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY) VALUES (2,'Khilan',25,'Delhi',1500);
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY) VALUES (3,'Kaushik',23,'Kota',2000);


```

**Output:**

<img width="1467" height="736" alt="image" src="https://github.com/user-attachments/assets/6fd05602-e027-4588-ad6f-245657f7d4fa" />



**Grade Page:**

<img width="1847" height="862" alt="image" src="https://github.com/user-attachments/assets/6f07f4f3-7a6d-4c32-9996-3a547fe586b8" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
