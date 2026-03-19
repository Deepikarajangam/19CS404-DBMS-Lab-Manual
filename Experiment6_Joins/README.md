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
--
-- Paste Question 1 here
<img width="1245" height="663" alt="image" src="https://github.com/user-attachments/assets/d29379ea-062c-474c-94a0-2cbc05682a46" />


```
SELECT p.first_name as patient_name FROM patients p
INNER JOIN test_results t
on p.patient_id=t.patient_id
where t.test_name='Blood Pressure';
```

**Output:**
<img width="1189" height="523" alt="image" src="https://github.com/user-attachments/assets/1949675b-4264-4ca7-97be-1a65aee776c2" />



**Question 2**
---
-- Paste Question 2 here
<img width="1238" height="782" alt="image" src="https://github.com/user-attachments/assets/d109da0d-f7bc-4a53-aac3-115b234822c9" />


```
SELECT c.cust_name,s.name from Customer c
LEFT JOIN Salesman s
    ON c.salesman_id=s.salesman_id
WHERE c.city=s.city;
```

**Output:**

<img width="1073" height="650" alt="image" src="https://github.com/user-attachments/assets/d7d0db00-a90b-413b-bdff-9977ac37d384" />


**Question 3**
---
<img width="1295" height="724" alt="image" src="https://github.com/user-attachments/assets/a21f107d-db7d-4d99-87b4-ec54d051bb17" />


```
SELECT c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt from customer c
LEFT JOIN orders o
on c.customer_id= o.customer_id
where c.city='London';
```

**Output:**

<img width="1256" height="600" alt="image" src="https://github.com/user-attachments/assets/35569e49-5752-40df-9161-52a94e719f8e" />


**Question 4**
---
<img width="1231" height="742" alt="image" src="https://github.com/user-attachments/assets/3ffb7e59-20fd-4271-8df9-97ad3e1a1f7b" />


```
SELECT p.first_name as patient_name, d.first_name as doctor_name from patients p
inner join doctors d
on p.doctor_id=d.doctor_id
where P.discharge_date is NULL;

```

**Output:**
<img width="1236" height="569" alt="image" src="https://github.com/user-attachments/assets/99f736d6-2dca-498c-a540-1a35a4322343" />



**Question 5**
---
-- Paste Question 5 here
<img width="1203" height="820" alt="image" src="https://github.com/user-attachments/assets/cfb3f110-664c-4ff2-ba8d-e94f62bebb8c" />

```
SELECT p.*,d.first_name as doctor_name from patients p
inner join doctors d
on p.doctor_id=d.doctor_id;
```

**Output:**
<img width="1234" height="660" alt="image" src="https://github.com/user-attachments/assets/1d5083a0-43ff-4d64-868b-4d8e83283620" />



**Question 6**
---
-- Paste Question 6 here
<img width="1242" height="696" alt="image" src="https://github.com/user-attachments/assets/45409c7b-9973-48fd-b888-e0039fce26d0" />

```
SELECT p.date_of_birth,a.* from patients p
inner join appointments a
on p.patient_id=a.patient_id
where p.first_name='Alice';
```

**Output:**

<img width="1234" height="509" alt="image" src="https://github.com/user-attachments/assets/25a03d8d-a207-4b63-9b29-516048fcb758" />


**Question 7**
---
-- Paste Question 7 here
<img width="1252" height="754" alt="image" src="https://github.com/user-attachments/assets/fc169c2f-72eb-4c2d-86f9-f8d49960b86f" />

```
SELECT c.cust_name,s.name from Customer c
LEFT JOIN Salesman s
    ON c.salesman_id=s.salesman_id
WHERE c.city=s.city;
```

**Output:**
<img width="1000" height="531" alt="image" src="https://github.com/user-attachments/assets/8505bb54-bcef-46d7-9b1c-9b2fc6863a0d" />



**Question 8**
---
-- Paste Question 8 here
<img width="1254" height="849" alt="image" src="https://github.com/user-attachments/assets/9d45edcf-9c03-4fd7-bdf7-115745771e8d" />

```
SELECT p.*,d.specialization as doctor_specialization from patients p
inner join doctors d
on p.doctor_id=d.doctor_id;
```

**Output:**

<img width="1217" height="655" alt="image" src="https://github.com/user-attachments/assets/3924126e-9280-4668-9ccb-2e271cb7d445" />


**Question 9**
---
-- Paste Question 9 here
<img width="1229" height="737" alt="image" src="https://github.com/user-attachments/assets/aa833469-0794-45da-948c-9abf43d0781c" />

```
SELECT n.*,d.department_name from nurses n
inner join departments d
on n.department_id=d.department_id;
```

**Output:**

<img width="1243" height="653" alt="image" src="https://github.com/user-attachments/assets/d60ba95a-7b7f-45c8-8c7c-a3bd1d122c59" />


**Question 10**
---
-- Paste Question 10 here
<img width="1195" height="697" alt="image" src="https://github.com/user-attachments/assets/cfa613bb-fa3f-4ff5-9156-f38b994a5d40" />

```
SELECT c.cust_name as 'Customer Name',c.city,s.name as Salesman, s.commission from customer c
inner join salesman s
on c.salesman_id=s.salesman_id;
```

**Output:**
<img width="1238" height="835" alt="image" src="https://github.com/user-attachments/assets/ee8eb73b-c994-4925-8f98-d99e6280a504" />




## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
