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

## Question 1

<img width="872" height="532" alt="image" src="https://github.com/user-attachments/assets/7e9fa27e-30bc-4060-aa14-43a5200d03c9" />

```
select order_no,order_date,purch_amt
from orders
where salesman_id=5001;
```

## Output:

<img width="861" height="400" alt="image" src="https://github.com/user-attachments/assets/af804572-cadd-4671-a1f7-502f78662bd9" />


## Question 2

<img width="1030" height="651" alt="image" src="https://github.com/user-attachments/assets/1b5b5233-34cc-4b54-8915-c916d8fa5305" />

```
DELETE FROM surgeries
WHERE surgery_id = 3
OR surgeon_id = 4;
```

## Output:

<img width="1202" height="917" alt="image" src="https://github.com/user-attachments/assets/b9888e50-287a-4f48-9f48-168dc5da8fa7" />


## Question 3

<img width="1202" height="537" alt="image" src="https://github.com/user-attachments/assets/ded5c403-c11d-4610-ace4-70f2463522bd" />

```
SELECT customer_id, city, grade, 'High Rating' as Rating
FROM customer
WHERE grade >= 300
UNION
SELECT customer_id, city, grade, 'Low Rating' as Rating
FROM customer
WHERE grade < 300;
```

## Output:

<img width="1136" height="530" alt="image" src="https://github.com/user-attachments/assets/0260ffc7-86fd-42a7-8a09-e870f6bf97d7" />


## Question 4

<img width="805" height="427" alt="image" src="https://github.com/user-attachments/assets/c01278af-75bf-4d17-a0cd-920a9be78594" />

```
SELECT CategoryName,
       Description
FROM Categories
ORDER BY CategoryName ASC;
```

## Output:

<img width="1202" height="520" alt="image" src="https://github.com/user-attachments/assets/4a1893ad-1479-4637-be29-50bf32c81a59" />


## Question 5

<img width="1032" height="705" alt="image" src="https://github.com/user-attachments/assets/133df865-2295-41c1-8c90-4a31710c1ff9" />

```
SELECT ename,hiredate,
       date(hiredate, '+100 days') AS DateAfter100Days
FROM emp;
```

## Output:

<img width="1021" height="356" alt="image" src="https://github.com/user-attachments/assets/a912f3fd-64fc-46d1-ad6e-375c7465fa49" />


## Question 6

<img width="1272" height="612" alt="image" src="https://github.com/user-attachments/assets/b0ce9769-e820-4050-a4cd-e8f56526e264" />

```
SELECT customer_id, cust_name, city, grade, salesman_id
FROM customer
WHERE grade IS NULL;
```

## Output:

<img width="1196" height="445" alt="image" src="https://github.com/user-attachments/assets/6f39e03f-7052-47cf-ae14-c41bff7ff5ef" />


## Question 7

<img width="640" height="676" alt="image" src="https://github.com/user-attachments/assets/c4384fd2-0b28-45fb-90a2-569a406b7280" />

```
SELECT lower(ename) AS EmpName FROM emp;
```

## Output:

<img width="467" height="550" alt="image" src="https://github.com/user-attachments/assets/dd4becbd-92b7-45c3-87c4-34b6c2cc64ab" />


## Question 8

<img width="992" height="171" alt="image" src="https://github.com/user-attachments/assets/8ea66844-6656-42e0-9677-92480bf59c85" />

```
DELETE FROM Doctors
WHERE doctor_id = 1;
```

## Output:

<img width="1202" height="240" alt="image" src="https://github.com/user-attachments/assets/c5356f4f-8e0b-406d-bf9a-0efa109c48dd" />


## Question 9

<img width="1227" height="437" alt="image" src="https://github.com/user-attachments/assets/011dbb77-8afc-4515-bab4-56efb3d0f832" />

```
select *
from customer
where city='London' and grade>200;
```

## Output:

<img width="1200" height="342" alt="image" src="https://github.com/user-attachments/assets/88f82013-56c2-4b7c-8de2-d2fedf75e18d" />


## Question 10

<img width="1217" height="637" alt="image" src="https://github.com/user-attachments/assets/20162431-baed-41f7-a7c5-362aaf00296f" />

```
UPDATE Employees
set salary=salary*2
where department_id=20
and job_id like '%MAN';
```

## Output:

<img width="1302" height="217" alt="image" src="https://github.com/user-attachments/assets/b4f380a9-bb96-458c-a27f-6ae95cce6040" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
