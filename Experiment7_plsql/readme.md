# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80

## INPUT:
```
DECLARE
    num1 NUMBER := 80;
    num2 NUMBER := 50;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
/
```
## OUTPUT:
<img width="781" height="315" alt="image" src="https://github.com/user-attachments/assets/8cc2eb01-18ff-4f7b-8b35-122549807d37" />


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55
## INPUT:
```
DECLARE
    n NUMBER := 10;
    i NUMBER := 1;
    sum NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```
## OUTPUT:
<img width="760" height="310" alt="image" src="https://github.com/user-attachments/assets/499be55f-ad73-4acb-89c9-3387c0d72759" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8
## INPUT:
```
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 7;     
    a NUMBER := 0;     
    b NUMBER := 1;    
    c NUMBER;          
    i NUMBER := 3;    
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);

    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;
```
## OUTPUT:
<img width="964" height="360" alt="image" src="https://github.com/user-attachments/assets/debb99a4-75d2-4eaf-83ad-ca2d267aac0f" />


---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351
## INPUT:
```
DECLARE
    n NUMBER := 1535;
    rev NUMBER := 0;
    rem NUMBER;
    temp NUMBER;
BEGIN
    temp := n;

    WHILE temp > 0 LOOP
        rem := MOD(temp, 10);        -- extract last digit
        rev := rev * 10 + rem;      -- build reversed number
        temp := FLOOR(temp / 10);   -- remove last digit
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/
```
## OUTPUT:
<img width="786" height="286" alt="image" src="https://github.com/user-attachments/assets/85530302-19e1-4e9d-b49e-25da0bade613" />


---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15
## INPUT:
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a > b AND a > c THEN
        largest := a;
    ELSIF b > a AND b > c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;

    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
/
```
## OUTPUT:
<img width="773" height="278" alt="image" src="https://github.com/user-attachments/assets/9966fab2-0b0a-41c1-a35c-390d581d8293" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
