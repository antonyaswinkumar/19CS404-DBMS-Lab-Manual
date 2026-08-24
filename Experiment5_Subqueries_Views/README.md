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
<img width="1199" height="662" alt="image" src="https://github.com/user-attachments/assets/4ab2f3d8-fa54-4901-82f3-6ee637f8e01c" />

## SQL QUERY : 
```
select id , name , age , city , income 
from Employee 
where age < (
    select avg(age)
    from Employee
    where income > 250000
);
```

**Output:**

<img width="1259" height="597" alt="image" src="https://github.com/user-attachments/assets/529463e3-da2a-46b7-a3c8-6c6d1f0ae04c" />


**Question 2**
---
<img width="1070" height="716" alt="image" src="https://github.com/user-attachments/assets/f10a0707-c72e-4394-868b-41e5a04dfe4f" />

## SQL QUERY : 
```
select customer_id , cust_name , city , grade , salesman_id
from customer
where customer_id = (
    select salesman_id
    from salesman
    where name = 'Mc Lyon'
)-2001;
```

**Output:**

<img width="1281" height="394" alt="image" src="https://github.com/user-attachments/assets/296c0f4e-f48b-4ec9-bef3-cc90c11d78fe" />


**Question 3**
---
<img width="1259" height="660" alt="image" src="https://github.com/user-attachments/assets/21c0907e-38a2-4ce2-9cd0-897fbe94a1a5" />

## SQL QUERY : 
```
select student_name , grade
from GRADES
where (subject , grade ) in (
    select subject , min(grade)
    from GRADES
    group by subject
);
```

**Output:**

<img width="897" height="513" alt="image" src="https://github.com/user-attachments/assets/700e7048-83ed-48b4-adb9-3694d3819ed9" />


**Question 4**
---
<img width="1248" height="514" alt="image" src="https://github.com/user-attachments/assets/fd3ce567-e9b6-4782-b98c-f67aae799fd2" />

## SQL QUERY : 
```
select grade , COUNT(*)
from customer
where grade > (
    select avg(grade)
    from customer
    where city = "New York"
)
group by grade;
```

**Output:**

<img width="859" height="414" alt="image" src="https://github.com/user-attachments/assets/61d11ff6-42ea-43fe-8890-48985e10b945" />


**Question 5**
---
<img width="1071" height="546" alt="image" src="https://github.com/user-attachments/assets/192ea167-6ff8-4095-a023-8c76b88978bc" />

## SQL QUERY : 
```
select id , name , city , email , phone
from customer
where city != (
    select city 
    from customer
    where id = (select max(id) from customer)
);
```

**Output:**

<img width="1245" height="574" alt="image" src="https://github.com/user-attachments/assets/be59d0f5-02bf-4ee2-a649-0f92b9bc4e6b" />


**Question 6**
---
<img width="1013" height="740" alt="image" src="https://github.com/user-attachments/assets/1777bc6e-6637-458c-a8a3-41d07125edc0" />

## SQL QUERY : 
```
select * from CUSTOMERS
where age < 30 
```

**Output:**

<img width="1242" height="661" alt="image" src="https://github.com/user-attachments/assets/648bec73-0f88-4595-bf65-49ddfd733057" />


**Question 7**
---
<img width="1059" height="738" alt="image" src="https://github.com/user-attachments/assets/7577c918-ab01-4087-9e05-b930dfcc5c36" />

## SQL QUERY : 
```
select * from CUSTOMERS
where salary > 1500
```

**Output:**

<img width="1227" height="683" alt="image" src="https://github.com/user-attachments/assets/ad96cb20-73fe-4889-9a27-4f1052fbd0e6" />


**Question 8**
---
<img width="1260" height="589" alt="image" src="https://github.com/user-attachments/assets/c6bf677c-cf8c-470c-8bfe-d6a1d9b39bdf" />

## SQL QUERY : 
```
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where salesman_id = (
    select salesman_id
    from orders
    where customer_id = 3007
);
```

**Output:**

<img width="1265" height="507" alt="image" src="https://github.com/user-attachments/assets/ec5bd74e-9356-4054-acf0-4fba95a76f2a" />


**Question 9**
---
<img width="1233" height="744" alt="image" src="https://github.com/user-attachments/assets/4e60d095-cebc-4b7f-8274-dba8d1ccbfaf" />

## SQL QUERY : 
```
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id = (
    SELECT salesman_id
    FROM salesman
    WHERE name = 'Paul Adam'
);
```

**Output:**

<img width="1289" height="475" alt="image" src="https://github.com/user-attachments/assets/cb00036c-80f6-4533-a19a-d2b9776600d3" />


**Question 10**
---
<img width="1118" height="625" alt="image" src="https://github.com/user-attachments/assets/2bfae937-d892-4537-a8c5-55a4ce6c3f51" />

## SQL QUERY : 
```
select * from CUSTOMERS
where ADDRESS = 'Delhi'
```

**Output:**

<img width="1246" height="403" alt="image" src="https://github.com/user-attachments/assets/b5cab2f8-1168-4962-af15-a4fb9497af11" />

## Grade:

<img width="1273" height="83" alt="image" src="https://github.com/user-attachments/assets/9dd7f44d-fee0-4e61-896f-7f60881419fe" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
