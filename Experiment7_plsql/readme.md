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

## SQL QUERY :
```
SET SERVEROUTPUT ON;

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

<img width="622" height="146" alt="image" src="https://github.com/user-attachments/assets/a20438a4-340b-4107-b7b1-9f8ec94dabb4" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55

## SQL QUERY:
```
DECLARE
    n   NUMBER := 10;   -- Value of N
    i   NUMBER := 1;    -- Loop counter
    sum NUMBER := 0;    -- Variable to store sum
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```

## OUTPUT :
<img width="791" height="155" alt="image" src="https://github.com/user-attachments/assets/6c6debe0-3388-4eb3-9027-c98df4aa080d" />


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

## SQL QUERY:
```
DECLARE
    n NUMBER := 7;       -- Number of terms to generate
    a NUMBER := 0;       -- First Fibonacci number
    b NUMBER := 1;       -- Second Fibonacci number
    c NUMBER;            -- Variable to hold next term
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');
    
    -- Print the first two terms
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);
    
    -- Loop to generate remaining terms
    FOR i IN 3..n LOOP
        c := a + b;          -- Next term
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;              -- Update values
        b := c;
    END LOOP;
END;
/
```

## OUTPUT :

<img width="453" height="246" alt="image" src="https://github.com/user-attachments/assets/7e979f94-075e-431e-8bea-f0196c28abe5" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

## SQL QUERY:
```
DECLARE
    n NUMBER := 1535;       -- Original number
    rev NUMBER := 0;        -- Variable to store reversed number
    digit NUMBER;           -- To hold each extracted digit
BEGIN
    WHILE n > 0 LOOP
        digit := MOD(n, 10);          -- Extract last digit
        rev := (rev * 10) + digit;    -- Build reversed number
        n := TRUNC(n / 10);           -- Remove last digit
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/

```
## OUTPUT :

<img width="585" height="130" alt="image" src="https://github.com/user-attachments/assets/7d8a35b9-11f3-4d1a-bb44-46a7cf1dae9a" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## SQL QUERY:
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a >= b AND a >= c THEN
        largest := a;
    ELSIF b >= a AND b >= c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;

    DBMS_OUTPUT.PUT_LINE('Largest of three numbers is ' || largest);
END;
/

```

## OUTPUT:
<img width="577" height="136" alt="image" src="https://github.com/user-attachments/assets/e6cc9079-7092-41a7-9ef6-feb5a10e5b0a" />

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
