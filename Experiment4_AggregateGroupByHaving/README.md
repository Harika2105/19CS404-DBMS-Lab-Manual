
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

## Question 1

<img width="1042" height="467" alt="image" src="https://github.com/user-attachments/assets/5ec40ac5-f8bb-4711-b91f-e3b6362705ec" />

```
SELECT AVG(income) AS avg_income
FROM employee
WHERE name LIKE 'A%';
```

 ## Output:

<img width="601" height="297" alt="image" src="https://github.com/user-attachments/assets/c6ec2807-f4bc-4b0d-953e-7f7ddbd1086e" />


## Question 2

<img width="1087" height="462" alt="image" src="https://github.com/user-attachments/assets/c6fb090b-5676-49bb-88a7-b9134ed21d3e" />

```
SELECT AVG(LENGTH(email)) AS avg_email_length_below_30
FROM customer 
WHERE city = 'Mumbai';
```

## Output:

<img width="725" height="302" alt="image" src="https://github.com/user-attachments/assets/cdaf10fe-9955-40a7-8d20-151206bac3cc" />


## Question 3

<img width="660" height="502" alt="image" src="https://github.com/user-attachments/assets/da9c590b-e3de-4632-a466-937da00e376d" />

```
SELECT MIN(purch_amt) AS MINIMUM
FROM orders;
```

## Output:

<img width="532" height="302" alt="image" src="https://github.com/user-attachments/assets/aa007f78-4032-427c-affd-b2a32cb4ba8b" />


## Question 4

<img width="1077" height="531" alt="image" src="https://github.com/user-attachments/assets/152b0e43-d91d-4b58-ac95-b3c7769c4393" />

```
SELECT DoctorID, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY DoctorID;
```

## Output:

<img width="735" height="612" alt="image" src="https://github.com/user-attachments/assets/fcba1176-78aa-40f3-9a90-4b6e4c0771d0" />


## Question 5

<img width="1107" height="562" alt="image" src="https://github.com/user-attachments/assets/e3019eff-1cb3-4247-9529-8b07413893e9" />

```
SELECT PatientID, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID;
```

## Output:

<img width="687" height="640" alt="image" src="https://github.com/user-attachments/assets/91ab5ada-964b-49fc-8dec-5e06c55b45f6" />


## Question 6

<img width="1015" height="571" alt="image" src="https://github.com/user-attachments/assets/96b69936-0bfd-4f75-8e3d-9dc678b3a484" />

```
SELECT DoctorID,
strftime('%H:%M',
AppointmentDateTime) AS TimeSlot,
COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID, TimeSlot
ORDER BY TotalAppointments DESC;
```

## Output:

<img width="1012" height="640" alt="image" src="https://github.com/user-attachments/assets/359bb221-497d-452f-948f-a2470e535263" />


## Question 7

<img width="1215" height="517" alt="image" src="https://github.com/user-attachments/assets/b1dd50b8-92cf-44a5-bd37-b0dcb685ade7" />

```
SELECT 
category_id,
SUM(price * category_id) AS Revenue
FROM
products
GROUP BY 
category_id
HAVING
SUM(price * category_id) > 25;
```

## Output:

<img width="685" height="412" alt="image" src="https://github.com/user-attachments/assets/279839ae-c67c-4183-86c2-9abce0881f11" />

## Question 8

<img width="1221" height="550" alt="image" src="https://github.com/user-attachments/assets/5fa6fea4-b1e4-4030-afb7-f88f02c42f2e" />

```
SELECT occupation, MIN(workhour)
FROM employee1
GROUP BY occupation
HAVING MIN(workhour) > 8;
```

## Output:

<img width="676" height="467" alt="image" src="https://github.com/user-attachments/assets/b9c0914a-cbd1-4994-b2e4-fa026f04f0c6" />


## Question 9

<img width="1217" height="512" alt="image" src="https://github.com/user-attachments/assets/387e5760-8a88-4b4e-8c52-639f27ca68d5" />

```
SELECT jdate, MIN(workhour)
FROM employee1
GROUP BY jdate
HAVING MIN(workhour) < 10;
```

## Output:

<img width="681" height="417" alt="image" src="https://github.com/user-attachments/assets/c07c6154-e222-4573-8b4c-8089728ef065" />


## Question 10

<img width="1222" height="452" alt="image" src="https://github.com/user-attachments/assets/9c0de56c-c2b0-40f8-9131-1da4d7ef925d" />

```
SELECT 
(age / 5) * 5 AS age_group,
AVG(age) AS "AVG(age)"
FROM 
customer1
GROUP BY
(age / 5) * 5
HAVING 
AVG(age) < 24;
```

## Output:

<img width="617" height="292" alt="image" src="https://github.com/user-attachments/assets/f0d114a4-fbe0-47cc-a7e7-0f35b2a6a2a6" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
