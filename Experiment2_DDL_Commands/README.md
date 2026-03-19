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
-- Paste Question 1 here
<img width="1237" height="550" alt="image" src="https://github.com/user-attachments/assets/8558d2e8-cd14-43a8-9d86-df83e3ec039f" />

```ALTER TABLE employee
ADD COLUMN department_id INTEGER;
ALTER TABLE employee
ADD COLUMN manager_id INTEGER DEFAULT NULL;
```

**Output:**

<img width="1224" height="405" alt="image" src="https://github.com/user-attachments/assets/45a8273e-d88e-4ff3-85ef-04be6d0b835a" />


**Question 2**
---
-- Paste Question 2 here
<img width="1270" height="635" alt="image" src="https://github.com/user-attachments/assets/5c668c02-c6b5-4a6c-8e54-43ac83c2fe13" />

```ALTER TABLE Student_details
ADD Mobilenumber number;
```

**Output:**

<img width="1232" height="442" alt="image" src="https://github.com/user-attachments/assets/a9c00f09-3472-48dc-92d9-80abe97918f2" />


**Question 3**
---
-- Paste Question 3 here
<img width="863" height="385" alt="image" src="https://github.com/user-attachments/assets/9630e3a6-72ae-4f70-ab85-c583d33e3abf" />

```CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT NOT NULL,
    Price REAL CHECK(Price>0),
    Stock INTEGER CHECK(Stock >=0)
  
  );
```

**Output:**

<img width="1214" height="334" alt="image" src="https://github.com/user-attachments/assets/b6d3f37f-acba-4a14-9959-675caa3d7a96" />


**Question 4**
---
-- Paste Question 4 here
<img width="1072" height="454" alt="image" src="https://github.com/user-attachments/assets/a38b16f2-9c5a-4073-82a4-062203f07678" />

```CREATE TABLE Events (
   EventID INTEGER,
   EventName TEXT,
   EventDate DATE

);
```

**Output:**

<img width="1229" height="471" alt="image" src="https://github.com/user-attachments/assets/677bb716-d4cb-4188-aebf-f7016115b20b" />

**Question 5**
---
-- Paste Question 5 here
<img width="1116" height="455" alt="image" src="https://github.com/user-attachments/assets/a3503cea-787f-4449-b4ac-b7972f60e393" />

```CREATE TABLE Locations (
    LocationID INTEGER,
    LocationName TEXT,
    Address TEXT

);
```

**Output:**

<img width="1239" height="461" alt="image" src="https://github.com/user-attachments/assets/40178cd0-2438-4787-ac6e-4d56996a3db0" />

**Question 6**
---
-- Paste Question 6 here
<img width="1192" height="540" alt="image" src="https://github.com/user-attachments/assets/3999ae60-b99e-426f-8aa1-55311e43b72f" />

```INSERT INTO Customers (ID, NAME,AGE,ADDRESS,SALARY)VALUES
(1, 'Ramesh', 32, 'Ahmedabad', 2000),
(2, 'Khilan', 25, 'Delhi', 1500),
(3, 'Kaushik', 23, 'Kota', 2000)
```

**Output:**

<img width="1247" height="386" alt="image" src="https://github.com/user-attachments/assets/ad76fbf1-2cba-438b-b95c-fcf2c6c91765" />

**Question 7**
---
-- Paste Question 7 here
<img width="1245" height="284" alt="image" src="https://github.com/user-attachments/assets/bb2e3a20-6bc6-446c-8c94-01d205612d47" />

```INSERT INTO Student_details(RollNo, Name, Gender, Subject, MARKS)
VALUES(201, 'David Lee', 'M', 'Physics', 92);
```

**Output:**

<img width="1232" height="319" alt="image" src="https://github.com/user-attachments/assets/1cde6b2e-a4aa-4ee6-97e3-150620af21fb" />


**Question 8**
---
-- Paste Question 8 here
<img width="1104" height="454" alt="image" src="https://github.com/user-attachments/assets/8857947c-a202-415c-aa3a-45b53a8db00d" />

```CREATE TABLE Employees (
    EmployeeID INTEGER,
    FirstName TEXT,
    LastName TEXT,
    HireDate DATE
);
```

**Output:**

<img width="1225" height="384" alt="image" src="https://github.com/user-attachments/assets/f49e9c3c-7298-4b64-80c5-4e15706f7122" />

**Question 9**
---
-- Paste Question 9 here
<img width="1015" height="429" alt="image" src="https://github.com/user-attachments/assets/5c361511-bd82-4d0c-a29c-bf38c765a190" />

```INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode) VALUES
(302 , 'Laura Croft', '456 Elm St', 'Seattle', 98101),
(303 , 'Bruce Wayne', '789 Oak St', 'Gotham', 10001)
```

**Output:**

<img width="1239" height="449" alt="image" src="https://github.com/user-attachments/assets/3ae74686-3a77-41c6-b447-e10da6c9e8f9" />


**Question 10**
---
-- Paste Question 10 here
<img width="1249" height="335" alt="image" src="https://github.com/user-attachments/assets/ee55b8d7-6b07-44b6-a73a-f5efe9acd3a3" />

```CREATE TABLE jobs (
    job_id INTEGER,
    job_title TEXT DEFAULT '',
    min_salary INTEGER DEFAULT 8000,
    max_salary INTEGER NULL

);
```

**Output:**

<img width="1237" height="436" alt="image" src="https://github.com/user-attachments/assets/4a374879-be30-484b-aedc-4d7d0546c19e" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
