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

## Question 1

<img width="961" height="457" alt="image" src="https://github.com/user-attachments/assets/509d338a-c929-4702-bf16-022a11977de8" />

```
CREATE TABLE Employees(
EmployeeID INTEGER,
FirstName TEXT,
LastName TEXT,
HireDate DATE
);
```

## Output:

<img width="1262" height="247" alt="image" src="https://github.com/user-attachments/assets/ce2e7370-71c9-48dc-b13a-d3a8bd09fea5" />


## Question 2

<img width="882" height="376" alt="image" src="https://github.com/user-attachments/assets/767fc2f8-ebf7-4e1a-a288-f9291effd7f8" />

```
CREATE TABLE Customers (
    CustomerID INTEGER,
    Name TEXT,
    Email TEXT,
    JoinDate DATETIME
);
```

## Output:

<img width="1362" height="181" alt="image" src="https://github.com/user-attachments/assets/fad8f423-06ee-462a-b68d-43242d0dc086" />


## Question 3

<img width="907" height="397" alt="image" src="https://github.com/user-attachments/assets/a345bdd6-53be-458d-b567-08a15a27c918" />

```
ALTER TABLE customer
ADD birth_date timestamp;

```

## Output:

<img width="1632" height="227" alt="image" src="https://github.com/user-attachments/assets/8f7739ba-6c4b-4b0d-9b94-1394a02defdf" />


## Question 4

<img width="1366" height="277" alt="image" src="https://github.com/user-attachments/assets/9fe4a35b-7fa1-4eac-a445-48e39593ddd2" />

```
CREATE TABLE Bonuses (
    BonusID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    BonusAmount REAL CHECK (BonusAmount > 0),
    BonusDate DATE,
    Reason TEXT NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

## Output:

<img width="1872" height="202" alt="image" src="https://github.com/user-attachments/assets/7b4a6e0e-d810-4717-a2be-ad2179c511df" />


## Question 5

<img width="716" height="245" alt="image" src="https://github.com/user-attachments/assets/6833b6ed-04d8-48f3-8cc5-6742b932892a" />

```
INSERT INTO Books (ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;
```


## Output:

<img width="1607" height="180" alt="image" src="https://github.com/user-attachments/assets/53d9b7a4-9edf-405f-bed5-7a144670e9be" />


## Question 6

<img width="1577" height="287" alt="image" src="https://github.com/user-attachments/assets/0d57d2e2-a149-4e99-ac07-bb1a0e4a5c85" />

```
CREATE TABLE contacts(
contact_id INTEGER primary key,
first_name TEXT not null,
last_name TEXT not null,
email TEXT,
phone TEXT not null check(length(phone)>=10));
```

## Output:

<img width="1821" height="202" alt="image" src="https://github.com/user-attachments/assets/f33c9d68-60ea-4472-8a99-e87c208852ad" />


## Question 7

<img width="1031" height="176" alt="image" src="https://github.com/user-attachments/assets/b5056e78-9555-4b95-8ede-85e493787568" />

```
INSERT into Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(201,'David Lee','M','Physics',92);
```

## Output:

<img width="1382" height="155" alt="image" src="https://github.com/user-attachments/assets/55319b22-b1d0-4965-8c2b-8b57c35c3b32" />


## Question 8

<img width="850" height="311" alt="image" src="https://github.com/user-attachments/assets/d0ea0dd2-b15c-41bb-90b4-87825b69a5c2" />

```
INSERT INTO Student_details VALUES(202,'Ella King','F','Chemistry',87),
(203,'James Bond','M','Literature',78);
```

## Output:

<img width="1181" height="167" alt="image" src="https://github.com/user-attachments/assets/466661be-ef8f-433b-8b27-65f1a27404c3" />


## Question 9

<img width="920" height="417" alt="image" src="https://github.com/user-attachments/assets/3711b85b-43ef-4040-980b-e02d23bb66f9" />

```
ALTER TABLE Student_details
ADD COLUMN Mobilenumber number;
```

## Output:

<img width="1427" height="232" alt="image" src="https://github.com/user-attachments/assets/2967bb40-45f9-484f-a054-10c4ff64cc8c" />


## Question 10 

<img width="1222" height="222" alt="image" src="https://github.com/user-attachments/assets/9ce2b0af-9ee7-4785-a626-a3b621639096" />

```
CREATE TABLE ProjectAssignments(
AssignmentID INTEGER primary key,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE not null,
foreign key(EmployeeID)references Employees(EmployeeID)
foreign key(ProjectID) references Projects(ProjectID)
);
```

## Output:

<img width="1587" height="177" alt="image" src="https://github.com/user-attachments/assets/3eb38674-a124-42fe-baf8-32aa8816ee1f" />

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
