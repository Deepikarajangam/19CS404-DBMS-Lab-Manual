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
-- Paste Question 1 here
<img width="1215" height="769" alt="image" src="https://github.com/user-attachments/assets/f7f8d864-39c5-46e5-8329-93f603186778" />

```UPDATE employees
SET first_name = 'John'
WHERE department_id = 80
   AND commission_pct < 0.35
```

**Output:**

<img width="1208" height="566" alt="image" src="https://github.com/user-attachments/assets/bdb34686-5cd2-4746-b78b-95319f837c18" />


**Question 2**
---
-- Paste Question 2 here
<img width="1206" height="565" alt="image" src="https://github.com/user-attachments/assets/bdeb7044-8575-4c51-a372-4c53411cc1f3" />

```DELETE FROM customer
WHERE (grade >2 AND payment_amt < (SELECT AVG(payment_amt) FROM customer))
OR outstanding_amt >8000;
```

**Output:**

<img width="1272" height="669" alt="image" src="https://github.com/user-attachments/assets/fb9fb702-aaa9-43c2-9206-0706d12832df" />


**Question 3**
---
-- Paste Question 3 here
<img width="1051" height="360" alt="image" src="https://github.com/user-attachments/assets/0d8b0394-94c0-45ed-87d6-4b43f8f6daa3" />

```UPDATE sales
SET sell_price = sell_price * 1.05
WHERE product_id = 15 AND sale_date = '2023-01-31';
```

**Output:**

<img width="1227" height="527" alt="image" src="https://github.com/user-attachments/assets/4d7d25c5-f60d-4a24-a2b6-5b5a0c4f8b71" />


**Question 4**
---
-- Paste Question 4 here
<img width="1000" height="457" alt="image" src="https://github.com/user-attachments/assets/e73b9538-0e32-4fb9-bacf-4452ed7d3991" />

```SELECT CategoryName, Description
FROM categories
ORDER BY CategoryName;
```

**Output:**

<img width="1216" height="640" alt="image" src="https://github.com/user-attachments/assets/3a178aa4-8456-49c8-8393-ab8f71e7faec" />


**Question 5**
---
-- Paste Question 5 here
<img width="1070" height="517" alt="image" src="https://github.com/user-attachments/assets/4de39f3f-181e-45d6-9f0d-d3d08fa89857" />

```UPDATE suppliers
SET address = '58 Lakeview, Magnolia'
WHERE supplier_id = 5;
```

**Output:**

<img width="1217" height="488" alt="image" src="https://github.com/user-attachments/assets/b1c95dd6-a79e-4fcf-8c5e-80c97c5b52b1" />


**Question 6**
---
-- Paste Question 6 here
<img width="1229" height="666" alt="image" src="https://github.com/user-attachments/assets/3c10b718-3165-470e-8dd7-6d8124a37d56" />

```DELETE FROM customer
WHERE grade >=2;
```

**Output:**

<img width="1189" height="644" alt="image" src="https://github.com/user-attachments/assets/409f3bd9-f672-4e55-bda9-a225723344fc" />


**Question 7**
---
-- Paste Question 7 here
<img width="1212" height="654" alt="image" src="https://github.com/user-attachments/assets/41bc286b-a774-42c2-8fcf-264cc9e81e5b" />

```SELECT ename,hiredate,JULIANDAY('2024-12-31') - JULIANDAY(hiredate) AS days_worked
FROM emp;
```

**Output:**

<img width="1045" height="371" alt="image" src="https://github.com/user-attachments/assets/9e6326d0-7e34-4402-9dcd-2e52e2890852" />

**Question 8**
---
-- Paste Question 8 here
<img width="1261" height="591" alt="image" src="https://github.com/user-attachments/assets/cee910e6-af88-4452-8490-a31ce4751b12" />

```UPDATE products
SET category = 'Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**

<img width="1238" height="591" alt="image" src="https://github.com/user-attachments/assets/5d206e80-6bc4-47a4-b2fd-3c1af2e676bb" />

**Question 9**
---
-- Paste Question 9 here
<img width="1254" height="612" alt="image" src="https://github.com/user-attachments/assets/0ebedcfa-dd2d-45be-b9fd-c248fb20b24b" />

```SELECT customer_id, city, grade, 'High Rating' AS Rating
FROM customer
WHERE grade>=300
UNION
SELECT customer_id,city,grade, 'Low Rating'
FROM customer
WHERE grade < 300;
```

**Output:**

<img width="1100" height="625" alt="image" src="https://github.com/user-attachments/assets/e67ecb08-f736-4209-a321-b3326cb51572" />


**Question 10**
---
-- Paste Question 10 here
<img width="1279" height="725" alt="image" src="https://github.com/user-attachments/assets/57999daf-46b4-4cf1-b2a9-54da7c1d8341" />

```DELETE FROM customer
WHERE grade < 2;
```

**Output:**

<img width="927" height="576" alt="image" src="https://github.com/user-attachments/assets/55eb2419-2d74-4f04-885e-e159cb7c32b8" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
