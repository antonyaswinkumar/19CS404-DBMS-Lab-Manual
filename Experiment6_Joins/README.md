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
<img width="1308" height="827" alt="image" src="https://github.com/user-attachments/assets/3d60d1be-fdbe-42cb-b6a1-a4e0d77e4340" />

## SQL QUERY :
```
select c.cust_name , c.city , o.ord_no , o.ord_date , o.purch_amt as "Order Amount" , s.name , s.commission 
from customer c
left join orders o
on c.customer_id = o.customer_id
left join salesman s
on c.salesman_id = s.salesman_id;
```

**Output:**

<img width="1318" height="667" alt="image" src="https://github.com/user-attachments/assets/3e7a20f8-2e29-4b23-b255-864ae0d5cbc6" />


**Question 2**
---
<img width="1276" height="658" alt="image" src="https://github.com/user-attachments/assets/5243635b-cb47-4d9a-94b5-99654b25cb8b" />

## SQL QUERY :
```
select p.admission_date , s.surgery_date 
from PATIENTS p
Inner join SURGERIES s
ON p.patient_id = s.surgery_id;
```

**Output:**

<img width="720" height="508" alt="image" src="https://github.com/user-attachments/assets/b06d3926-6cfa-4700-b02f-c4216c49d716" />

**Question 3**
---
<img width="1298" height="517" alt="image" src="https://github.com/user-attachments/assets/a1e76e7e-90ed-4fc0-b8ef-e4df99c23a0e" />

## SQL QUERY :
```
select c.cust_name ,o.ord_no,o.ord_date,o.purch_amt
from customer c
left join orders o
on c.customer_id = o.customer_id;

```

**Output:**

<img width="1222" height="705" alt="image" src="https://github.com/user-attachments/assets/1d28f2ba-ea5d-4017-a1ed-e67a83e59b56" />


**Question 4**
---
<img width="1313" height="763" alt="image" src="https://github.com/user-attachments/assets/8efaf635-3823-47fd-8193-8f51d396421c" />

## SQL QUERY :
```
select c.cust_name as "Customer Name" , c.city , s.name as "Salesman" , s.commission
from customer c
join salesman s
on c.salesman_id = s.salesman_id
where s.commission > 0.12 ;
```

**Output:**

<img width="1182" height="667" alt="image" src="https://github.com/user-attachments/assets/616f1848-8f4b-4898-8d49-7a3bd1b98e47" />


**Question 5**
---
<img width="1290" height="627" alt="image" src="https://github.com/user-attachments/assets/1d5857fc-2c0d-4dee-ba88-cc7df1784503" />

## SQL QUERY :
```
select p.first_name as "patient_name" , d.specialization as "Doctor_speciali"
from PATIENTS p
inner join DOCTORS d
on p.doctor_id = d.doctor_id
where p.admission_date between '2024-01-01' and '2024-01-31' ;
```

**Output:**

<img width="695" height="372" alt="image" src="https://github.com/user-attachments/assets/8bae052c-fb28-443d-9cf2-359b92c375a8" />


**Question 6**
---
<img width="1210" height="780" alt="image" src="https://github.com/user-attachments/assets/dfac2559-deb6-4741-af62-3036b0d693e1" />

## SQL QUERY :
```
select c.cust_name as "Customer Name" , c.city , s.name as "Salesman" , s.commission
from customer c
join salesman s
on c.salesman_id = s.salesman_id ;
```

**Output:**

<img width="1258" height="807" alt="image" src="https://github.com/user-attachments/assets/d1c7fad7-2464-413a-88cb-1b86ea622d7c" />


**Question 7**
---
<img width="1305" height="642" alt="image" src="https://github.com/user-attachments/assets/f89a8dbc-124c-4a86-9446-bf522bae68b8" />

## SQL QUERY :
```
select p.first_name , s.* 
from PATIENTS p
inner join SURGERIES s
on p.patient_id = s.patient_id
where p.date_of_birth > '1990-01-01' ;
```

**Output:**

<img width="1312" height="377" alt="image" src="https://github.com/user-attachments/assets/70a82a3e-2d71-45f3-bd49-47fbaee50a69" />


**Question 8**
---
<img width="1302" height="763" alt="image" src="https://github.com/user-attachments/assets/d8438497-9a53-4bd5-888f-c14d56360438" />

## SQL QUERY :
```
select c.cust_name , c.city , c.grade , s.name as "Salesman" , s.city
from customer c 
join salesman s
on c.salesman_id = s.salesman_id
where c.grade < 300 
order by c.customer_id asc;
```

**Output:**

<img width="1312" height="687" alt="image" src="https://github.com/user-attachments/assets/e07d78eb-0c2f-4cd3-a350-0e77ec6b4f0c" />


**Question 9**
---
<img width="1287" height="732" alt="image" src="https://github.com/user-attachments/assets/a8dc9a8d-4a32-4f36-9326-f6caea9ea90b" />

## SQL QUERY :
```
select c.cust_name as "Customer Name" , c.city , s.name as "Salesman" , s.city , s.commission
from customer c
join salesman s
on c.salesman_id = s.salesman_id
where c.city <> s.city and s.commission > 0.12 ;
```

**Output:**

<img width="1313" height="541" alt="image" src="https://github.com/user-attachments/assets/1c519a5a-7f83-4ffd-a60c-47faf0d135cd" />


**Question 10**
---

<img width="1286" height="310" alt="image" src="https://github.com/user-attachments/assets/ef37439c-8462-461f-ad8d-e79c38a16ef2" />

## SQL QUERY :
```
select c.cust_name 
from customer c
left join orders o 
on c.customer_id = o.customer_id
where o.purch_amt < 100 ;
```

**Output:**

<img width="517" height="443" alt="image" src="https://github.com/user-attachments/assets/90d19939-bff9-492e-a5a4-5505386b3b3f" />

## Grade :
<img width="1256" height="70" alt="image" src="https://github.com/user-attachments/assets/69b9e601-bf6d-4f41-b55e-40bb60e3e418" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
