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

## Question 1

<img width="1237" height="670" alt="image" src="https://github.com/user-attachments/assets/65cd429f-a948-42ab-a8e1-d66b58c2e137" />

```
SELECT 
c.cust_name,
c.city,
o.ord_no,
o.ord_date,
o.purch_amt
FROM
customer c
LEFT JOIN
orders o ON c.customer_id = o.customer_id
WHERE
c.city ='London';
```

## Output:

<img width="1216" height="487" alt="image" src="https://github.com/user-attachments/assets/90968942-b908-4e17-9bec-89f26cf5a858" />


## Question 2

<img width="1277" height="737" alt="image" src="https://github.com/user-attachments/assets/7a65dee7-b090-4491-8718-f90e9c4b3ef9" />

```
SELECT c.cust_name , s.name
FROM customer c
LEFT JOIN salesman s on c.salesman_id = s.salesman_id
WHERE c.city == s.city
```

## Output:

<img width="972" height="537" alt="image" src="https://github.com/user-attachments/assets/e561fa9a-f68d-4ea6-aa95-071e856438bc" />


## Question 3

<img width="1215" height="646" alt="image" src="https://github.com/user-attachments/assets/0619cfe3-675d-4b0b-9c97-96f35f3d4df8" />

```
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id   
WHERE o.ord_date BETWEEN '2012-08-01' AND '2012-08-30'
```

## Output:

<img width="1207" height="482" alt="image" src="https://github.com/user-attachments/assets/6d5efb06-dd96-4887-96fb-c48fb58bef7d" />


## Question 4

<img width="1187" height="977" alt="image" src="https://github.com/user-attachments/assets/6870a9db-29c4-4e07-9f31-ff31ad33d9ba" />

```
SELECT a.ord_no, a.ord_date, a.purch_amt,
       b.cust_name AS "Customer Name", b.grade, 
       c.name AS "Salesman", c.commission 
FROM orders a 
INNER JOIN customer b 
ON a.customer_id = b.customer_id 
INNER JOIN salesman c 
ON a.salesman_id = c.salesman_id;
```

## Output:

<img width="1246" height="907" alt="image" src="https://github.com/user-attachments/assets/c6a6c1ca-224e-4a53-8e07-fed168aa9d7a" />


## Question 5

<img width="1297" height="670" alt="image" src="https://github.com/user-attachments/assets/14e0f9e6-b670-499d-85d8-da140faaba79" />

```
SELECT s.name as salesman_name,  c.cust_name as customer_name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
```

## Output:

<img width="692" height="747" alt="image" src="https://github.com/user-attachments/assets/250702fc-10d9-46fd-a4de-de76e58ef40a" />


## Question 6

<img width="1282" height="527" alt="image" src="https://github.com/user-attachments/assets/212bda9d-193e-4f43-849f-c30e8487413f" />

```
SELECT p.first_name as patient_name , t.test_name
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id
```

##  Output:

<img width="686" height="425" alt="image" src="https://github.com/user-attachments/assets/489fe074-1309-4f5f-abc3-ab982e483be9" />


## Question 7

<img width="1317" height="502" alt="image" src="https://github.com/user-attachments/assets/28cf61f6-8c0c-4c67-ac70-ca48724ac6cd" />

```
select p.* from patients p
inner join test_results tr on p.patient_id=tr.patient_id
where test_name like "X-Ray" and result="Normal";
```

## Output:

<img width="1272" height="361" alt="image" src="https://github.com/user-attachments/assets/ac98caed-5cc7-4c1f-9a38-f383fb23c497" />


## Question 8

<img width="1287" height="501" alt="image" src="https://github.com/user-attachments/assets/d641662c-b931-45bb-8197-d420d068ecf0" />

```
SELECT p.*
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id
WHERE (t.test_name = 'Blood Test' or t.test_name = 'Blood Pressure') AND t.result NOT LIKE '%Normal%'
```

## Output:

<img width="1271" height="336" alt="image" src="https://github.com/user-attachments/assets/f94e062e-2b6b-460c-90e7-3e5922d12a02" />



## Question 9

<img width="1277" height="772" alt="image" src="https://github.com/user-attachments/assets/6890255c-c670-448c-ae22-b4959252de3e" />


```
SELECT a.cust_name AS "Customer Name", 
       a.city, 
       b.name AS "Salesman", 
       b.commission 
-- Specifying the tables to retrieve data from ('customer' as 'a' and 'salesman' as 'b')
FROM customer a 
-- Performing an inner join based on the salesman_id
INNER JOIN salesman b 
ON a.salesman_id = b.salesman_id 
-- Filtering the results based on a condition (commission greater than 0.12)
WHERE b.commission > 0.12;
```

## Output:

<img width="1197" height="606" alt="image" src="https://github.com/user-attachments/assets/97ffc8db-bee4-49dd-bb02-74edc05c57c1" />


## Question 10

<img width="1232" height="516" alt="image" src="https://github.com/user-attachments/assets/6695c77f-c674-4f6b-8e9d-fcab2b81f55f" />

```
SELECT c.cust_name
FROM customer c 
left JOIN orders o
ON c.customer_id = o.customer_id
where o.purch_amt<100
```
**Output:**

<img width="417" height="377" alt="image" src="https://github.com/user-attachments/assets/d66b8fdd-7168-410a-bcaf-3fdc90044671" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
