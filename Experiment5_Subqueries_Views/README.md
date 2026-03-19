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
--
-- Paste Question 1 here
<img width="1145" height="670" alt="image" src="https://github.com/user-attachments/assets/ed5a732d-9698-4226-a730-4f5e0ffe7283" />

```
SELECT * FROM Employee
where age <(SELECT AVG(age) as age from Employee
where income>1000000
);
```

**Output:**

<img width="1222" height="525" alt="image" src="https://github.com/user-attachments/assets/e379088f-a89f-4e00-b51d-7937d0ccf787" />

**Question 2**
---
<img width="1065" height="719" alt="image" src="https://github.com/user-attachments/assets/4fe33cf0-6938-4815-a50f-92a95afdeea0" />


```
SELECT * FROM CUSTOMERS
where SALARY > 4500;
```

**Output:**
<img width="1230" height="538" alt="image" src="https://github.com/user-attachments/assets/8e87b67e-81fa-414e-a0ba-199aad888439" />


**Question 3**
---
-- Paste Question 3 here
<img width="1140" height="702" alt="image" src="https://github.com/user-attachments/assets/641d175e-41b4-43cb-9373-9ad5beacebd1" />

```
SELECT * FROM CUSTOMERS
where SALARY = 1500;
```

**Output:**

<img width="1211" height="447" alt="image" src="https://github.com/user-attachments/assets/ad991aae-4cd3-452e-a710-b7957a95d25e" />


**Question 4**
---
-- Paste Question 4 here
<img width="1249" height="709" alt="image" src="https://github.com/user-attachments/assets/d30d1718-66d8-4f91-81d4-d6c7a0f4016c" />

```SELECT * FROM Orders
where salesman_id in(select salesman_id from Salesman
where city='London');
```

**Output:**

<img width="1245" height="481" alt="image" src="https://github.com/user-attachments/assets/5b7b611c-ab98-4551-b8bf-f5c3edb3a223" />


**Question 5**
---
-- Paste Question 5 here
<img width="1120" height="590" alt="image" src="https://github.com/user-attachments/assets/031965a1-642b-48fc-b406-c163383363f3" />

```SELECT * from customer
where city<>(select city from customer 
order by id DESC
LIMIT 1);
```

**Output:**

<img width="1227" height="529" alt="image" src="https://github.com/user-attachments/assets/dd300313-5661-4726-8904-48228cfd98fe" />


**Question 6**
---
-- Paste Question 6 here
<img width="1114" height="541" alt="image" src="https://github.com/user-attachments/assets/ad18ad85-4644-4c33-8254-c851726327fa" />

```SELECT medication_id as medic,medication_name,dosage from Medications
where dosage =(select max(dosage) from Medications);
```

**Output:**

<img width="1103" height="512" alt="image" src="https://github.com/user-attachments/assets/bd89e1e5-300c-47d9-b496-e5e83b3ec779" />


**Question 7**
---
-- Paste Question 7 here
<img width="1125" height="729" alt="image" src="https://github.com/user-attachments/assets/c439231d-2996-4033-b00c-f4bec3d2e535" />

```SELECT * FROM customer
where customer_id in((Select salesman_id from salesman where name='Mc Lyon')-2001);

```

**Output:**

<img width="1233" height="388" alt="image" src="https://github.com/user-attachments/assets/df28d308-a960-4027-8df2-cedc7b88a809" />


**Question 8**
---
<img width="1231" height="665" alt="image" src="https://github.com/user-attachments/assets/7c8ec6a9-960c-452c-aeea-58d321c63524" />


```SELECT * FROM ORDERS
where purch_amt >( select avg(purch_amt) from ORDERS
where ord_date='2012-10-10'
);
```

**Output:**

<img width="1230" height="573" alt="image" src="https://github.com/user-attachments/assets/aeb1454b-18e4-4d8a-8b3a-1f9c751b90dc" />


**Question 9**
---
-- Paste Question 9 here
<img width="1344" height="729" alt="image" src="https://github.com/user-attachments/assets/b4043ed7-66fe-4747-ae6f-c613919540e6" />

```SELECT * FROM GRADES g1
where grade in(select min(grade) from GRADES g2
where g2.subject=g1.subject
);
```

**Output:**

<img width="1243" height="554" alt="image" src="https://github.com/user-attachments/assets/35aac0cc-59f4-4860-a7fd-8bdc6dac5b53" />


**Question 10**
---
-- Paste Question 10 here
<img width="1110" height="702" alt="image" src="https://github.com/user-attachments/assets/03284437-e967-4aa5-863a-0d6068fa8a46" />

```SELECT commission from salesman
where salesman_id in (select salesman_id from customer
where city='Paris');
```

**Output:**

<img width="795" height="495" alt="image" src="https://github.com/user-attachments/assets/ecc4c119-2617-40ea-9230-9582aa832618" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
