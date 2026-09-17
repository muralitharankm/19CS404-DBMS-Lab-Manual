\# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**

<img width="652" height="449" alt="image" src="https://github.com/user-attachments/assets/bf85612d-e627-4318-aee8-47cf7112059c" />


```sql
SELECT 
    DATE(AppointmentDateTime) AS AppointmentDate,
    COUNT(*) AS TotalAppointments
FROM 
    Appointments
GROUP BY 
    DATE(AppointmentDateTime)
ORDER BY 
    AppointmentDate;
```

**Output:**

<img width="735" height="502" alt="image" src="https://github.com/user-attachments/assets/ea9bbee4-ed5c-4260-8e56-2316dbbe6ddf" />


**Question 2**

<img width="772" height="433" alt="image" src="https://github.com/user-attachments/assets/b6a3eb23-8e33-479e-9e74-95e35bc3e6c2" />


```sql
SELECT
  Medication,
  AVG(Dosage) AS AvgDosage
FROM
  Prescriptions
GROUP BY
  Medication
ORDER BY
  Medication;
```

**Output:**

<img width="603" height="562" alt="image" src="https://github.com/user-attachments/assets/27261e4b-5686-4985-8f18-981374addd41" />


**Question 3**

<img width="836" height="336" alt="image" src="https://github.com/user-attachments/assets/0abf57cc-f454-44f2-be0d-be84393634f9" />


```sql
SELECT
  strftime('%Y-%m', Date) AS Month,
  COUNT(*) AS TotalRecords
FROM
  MedicalRecords
GROUP BY
  Month
ORDER BY
  Month;
```

**Output:**

<img width="763" height="358" alt="image" src="https://github.com/user-attachments/assets/134abf33-7506-4d38-9e6e-cdbca2a780f3" />


**Question 4**

<img width="745" height="327" alt="image" src="https://github.com/user-attachments/assets/1128fa15-3f96-4f14-9ea9-dd15e3c7ec64" />


```sql
SELECT SUM(purch_amt) AS TOTAL
FROM orders;
```

**Output:**

<img width="775" height="274" alt="image" src="https://github.com/user-attachments/assets/d0d226c2-ab13-43bd-9413-63843db36870" />


**Question 5**

<img width="754" height="328" alt="image" src="https://github.com/user-attachments/assets/9524bef6-937b-4c78-8df9-94c0d2f0c02f" />


```sql
SELECT SUM(income) AS total_income
FROM employee
WHERE age >= 40;
```

**Output:**

<img width="827" height="274" alt="image" src="https://github.com/user-attachments/assets/49084b3f-d8a4-4b05-94ae-736496d2a564" />


**Question 6**

<img width="721" height="349" alt="image" src="https://github.com/user-attachments/assets/fe713f22-aea9-4d93-b205-755701e6d2c9" />


```sql

SELECT name AS Employee_Name, age AS Age
FROM employee
ORDER BY age ASC, id ASC
LIMIT 1;
```

**Output:**

<img width="873" height="271" alt="image" src="https://github.com/user-attachments/assets/e731e0d7-4dee-43ea-8968-8127ff04e396" />


**Question 7**

<img width="710" height="369" alt="image" src="https://github.com/user-attachments/assets/c6b4e149-27f6-4615-85e2-75e4e3038368" />


```sql
SELECT SUM(inventory) AS total
FROM fruits
WHERE unit = 'LB';
```

**Output:**

<img width="865" height="276" alt="image" src="https://github.com/user-attachments/assets/e61df743-c6cf-4b7e-b65b-314ec72d6d83" />


**Question 8**

<img width="742" height="347" alt="image" src="https://github.com/user-attachments/assets/4da91163-36b1-48cf-aa2d-3d24ede0f3e3" />


```sql
SELECT PatientID, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID
HAVING COUNT(*) > 3;
```

**Output:**

<img width="907" height="286" alt="image" src="https://github.com/user-attachments/assets/31d75ca5-6e9a-4d3f-aa26-2d46820f9c60" />


**Question 9**

<img width="832" height="301" alt="image" src="https://github.com/user-attachments/assets/1ac9a4e8-5f2a-45a6-a3b9-9e77b2169d70" />


```sql
SELECT Diagnosis, COUNT(*) AS DiagnosisCount
FROM MedicalRecords
GROUP BY Diagnosis
ORDER BY DiagnosisCount DESC
LIMIT 1;
```

**Output:**

<img width="836" height="273" alt="image" src="https://github.com/user-attachments/assets/5aefcb2b-1646-4afd-ba35-7c3cccecebe6" />


**Question 10**

<img width="872" height="368" alt="image" src="https://github.com/user-attachments/assets/8dc011cc-825f-413d-ac91-fe4720f771ef" />


```sql
SELECT DoctorID, COUNT(AppointmentID) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```

**Output:**

<img width="892" height="481" alt="image" src="https://github.com/user-attachments/assets/1bc378ae-1021-4c73-af99-d5d5238f0bab" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
