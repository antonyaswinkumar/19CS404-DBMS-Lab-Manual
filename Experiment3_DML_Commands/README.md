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
<img width="1116" height="223" alt="image" src="https://github.com/user-attachments/assets/5e716d33-b1c8-4c44-b285-60f005c163e8" />

```
UPDATE products
SET availability = availability * 2
WHERE product_id = 1 ;
```

**Output:**

<img width="1218" height="802" alt="image" src="https://github.com/user-attachments/assets/de197f49-71ca-44d3-8739-c512717cf282" />


**Question 2**
---
<img width="1072" height="477" alt="image" src="https://github.com/user-attachments/assets/c3b8cecc-07de-4b10-9202-ef7432a2c946" />


```
UPDATE suppliers
SET supplier_name = UPPER(supplier_name)
WHERE contact_person LIKE '%Singh%' ;
```

**Output:**

<img width="1223" height="852" alt="image" src="https://github.com/user-attachments/assets/22a9521c-688f-4ac7-b5f0-5cfb8add6d8c" />


**Question 3**
---
<img width="1172" height="231" alt="image" src="https://github.com/user-attachments/assets/4eaff034-8f30-4939-90c4-8befeb8bd0ed" />


```
UPDATE products
SET product_name = 'Grapefruit'
WHERE product_id = 4 ;`

```

**Output:**

<img width="1230" height="820" alt="image" src="https://github.com/user-attachments/assets/9bc53f4b-8019-4246-917c-8b481ae814ae" />


**Question 4**
---
<img width="1215" height="552" alt="image" src="https://github.com/user-attachments/assets/bf5c6060-d99e-44a9-ae57-2a245a74cc59" />


```
UPDATE products
SET reorder_lvl = reorder_lvl + reorder_lvl* 0.3
WHERE category ='Food'
      AND quantity < 0.5 * reorder_lvl;
```

**Output:**

<img width="1227" height="851" alt="Screenshot 2026-08-07 112954" src="https://github.com/user-attachments/assets/e724852e-92ac-4e29-a720-ddd3e9f21c0a" />


**Question 5**
---

<img width="1226" height="567" alt="image" src="https://github.com/user-attachments/assets/3f2e67c5-77f6-4baa-ba3e-732c63f24009" />


```
DELETE FROM Customer
WHERE GRADE >=3 AND CUST_COUNTRY NOT IN ('UK','USA','Canada');
```

**Output:**

<img width="1227" height="851" alt="image" src="https://github.com/user-attachments/assets/e4977a29-b44a-456c-8e6a-042fe2afbe8f" />

**Question 6**
---

<img width="1020" height="563" alt="image" src="https://github.com/user-attachments/assets/c47fd095-b3bd-4b88-8ff9-da1a09d055b3" />


```
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**


<img width="1222" height="852" alt="image" src="https://github.com/user-attachments/assets/2ff26582-a0db-4bf1-982f-509a67c21ea1" />


**Question 7**
---

<img width="1221" height="627" alt="image" src="https://github.com/user-attachments/assets/34172b18-feff-4b9b-9598-53ca9634f10c" />


```
SELECT *FROM customer
WHERE grade IS NULL ;
```

**Output:**


<img width="1230" height="852" alt="image" src="https://github.com/user-attachments/assets/1117ecc3-ef3c-44f1-98f0-db53daad3a76" />


**Question 8**
---

<img width="1172" height="621" alt="image" src="https://github.com/user-attachments/assets/2e11fec9-0ca4-43fa-b1cb-2b0fd54dc92c" />


```
SELECT *,(original_price *discount_percentage) AS discount_amount
FROM Products
WHERE discount_amount > 50;
```

**Output:**


<img width="1223" height="800" alt="image" src="https://github.com/user-attachments/assets/73fd7e05-e7b0-4830-8b04-796900e21af4" />


**Question 9**
---

<img width="1040" height="595" alt="image" src="https://github.com/user-attachments/assets/c6d19507-53bf-4e2c-a54e-d98e83e90973" />


```
SELECT ename , hiredate , strftime('%w',hiredate) AS  day_of_week
FROM emp
WHERE strftime('%w',hiredate) IN ('0','6');
```

**Output:**


<img width="1183" height="837" alt="image" src="https://github.com/user-attachments/assets/5c1a6873-c69d-46c3-8bb3-0b0d181ce93c" />


**Question 10**
---

<img width="1157" height="551" alt="image" src="https://github.com/user-attachments/assets/fe35d569-0362-4c0d-8742-a55b3121e47f" />


```
SELECT first_name,last_name,(julianday(discharge_date)-julianday(admission_date) +1 ) AS no_of_days
FROM Patients
WHERE no_of_days > 3;
```

**Output:**


<img width="1212" height="831" alt="image" src="https://github.com/user-attachments/assets/5794e010-ec3f-4c06-90d9-a07f912e0745" />



**Grade:**

<img width="1386" height="85" alt="image" src="https://github.com/user-attachments/assets/59290ea6-76c6-4347-a348-589a346d1b5f" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
