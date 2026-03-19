# Experiment 4: Aggregate Functions, Group By and Having Clause

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
--
-- Paste Question 1 here
<img width="1004" height="506" alt="image" src="https://github.com/user-attachments/assets/b58a4e31-ac44-41c6-baa2-e276a9b4d805" />

```SELECT AVG(purch_amt)as AVERAGE from orders;
```

**Output:**

<img width="697" height="398" alt="image" src="https://github.com/user-attachments/assets/d5f4f637-fbb1-4815-9f24-e3ed77db0258" />


**Question 2**
---
-- Paste Question 2 here
<img width="1060" height="523" alt="image" src="https://github.com/user-attachments/assets/18be6993-c575-4adf-bfb8-3a6fb0b61bf0" />

```SELECT MAX(price)-MIN(price) as price_diff from fruits;
```

**Output:**

<img width="860" height="413" alt="image" src="https://github.com/user-attachments/assets/76d59746-8887-45bf-909b-d04a4fac2796" />


**Question 3**
---
-- Paste Question 3 here
<img width="850" height="506" alt="image" src="https://github.com/user-attachments/assets/46dbb9b1-6471-4cb8-9da2-fae44c09b867" />

```SELECT MIN(purch_amt) as MINIMUM from orders;
```

**Output:**

<img width="868" height="386" alt="image" src="https://github.com/user-attachments/assets/9d0e1b57-ecbf-489e-a7d0-eb54e1ab8d16" />


**Question 4**
---
-- Paste Question 4 here
<img width="1131" height="574" alt="image" src="https://github.com/user-attachments/assets/223b00a9-87b0-4923-aff3-4c7d2a774833" />

```SELECT DoctorID,count(AppointmentID) as TotalAppointments from Appointments
group by DoctorID;
```

**Output:**

<img width="974" height="622" alt="image" src="https://github.com/user-attachments/assets/d2897f91-c764-4db1-98ce-01190c33fe41" />

**Question 5**
---
-- Paste Question 5 here
<img width="1158" height="612" alt="image" src="https://github.com/user-attachments/assets/51d7cc05-690b-4dfe-8a00-8e2e018a51f6" />

```SELECT Specialty,Gender,count(Gender) as TotalDoctors from Doctors
group by Specialty,Gender
order by Specialty,Gender;

```

**Output:**

<img width="1101" height="749" alt="image" src="https://github.com/user-attachments/assets/4bb58212-2540-42d4-bcdf-281b0acb0540" />


**Question 6**
---
-- Paste Question 6 here
<img width="944" height="519" alt="image" src="https://github.com/user-attachments/assets/c45ab82d-71cb-4c60-96d9-342215563d60" />

```SELECT MIN(purch_amt) as MINIMUM from orders;
```

**Output:**

<img width="912" height="427" alt="image" src="https://github.com/user-attachments/assets/a32d9b3e-1428-48f1-90c0-c2de5494dce9" />


**Question 7**
---
-- Paste Question 7 here
<img width="1181" height="547" alt="image" src="https://github.com/user-attachments/assets/e2cae2a1-61ba-4a6f-ab8e-7966e144b039" />

```SELECT (age/5)*5 as age_group,SUM(salary) from customer1
group by age_group
having SUM(salary)>5000;
```

**Output:**

<img width="1064" height="475" alt="image" src="https://github.com/user-attachments/assets/977610a8-c144-4486-9c76-4f3f6676f064" />


**Question 8**
---
-- Paste Question 8 here
<img width="1223" height="587" alt="image" src="https://github.com/user-attachments/assets/f733e131-fbeb-455a-a198-0d27045468ac" />

```SELECT city,AVG(income)from employee
group by city
having AVG(income)>500000;
```

**Output:**

<img width="997" height="510" alt="image" src="https://github.com/user-attachments/assets/aac4b165-14b2-492a-9029-f8141c37dc36" />


**Question 9**
---
-- Paste Question 9 here
<img width="1167" height="573" alt="image" src="https://github.com/user-attachments/assets/81cf01aa-68a2-48b1-9057-5c4cd060a441" />

```SELECT address,SUM(salary)from customer1
group by address
having SUM(salary)>2000;
```

**Output:**

<img width="1044" height="567" alt="image" src="https://github.com/user-attachments/assets/ad98e414-e492-4c59-bfa0-e9431665d59c" />


**Question 10**
---
-- Paste Question 10 here
<img width="1251" height="574" alt="image" src="https://github.com/user-attachments/assets/0173442d-b0b0-405b-a7e4-ccddd8f34736" />

```SELECT jdate,MIN(workhour) from employee1
group by jdate
having MIN(workhour)<10;
```

**Output:**

<img width="927" height="507" alt="image" src="https://github.com/user-attachments/assets/fbe1549a-fa9e-4e08-aa8a-ff566169ac8c" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
