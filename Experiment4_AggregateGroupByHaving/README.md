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

<img width="1196" height="643" alt="image" src="https://github.com/user-attachments/assets/3512fec7-3830-48b3-81b5-4e3251969eac" />

```
SELECT InsuranceCompany , Count(PatientID) as TotalExpiredPatients
FROM Insurance
WHERE ValidityPeriod < CURRENT_DATE
Group by InsuranceCompany;

```

**Output:**

<img width="1008" height="827" alt="image" src="https://github.com/user-attachments/assets/d4d2a8ce-ed9d-4acb-b483-871227a34519" />

**Question 2**
---
<img width="1184" height="460" alt="image" src="https://github.com/user-attachments/assets/6818389d-244c-4456-8667-5f54ae761c19" />

```
SELECT SUBSTR(Email,INSTR(Email,'@')+1) AS EmailDomain, count(*) AS TotalPatients
FROM Patients
group by EmailDomain;
```

**Output:**

<img width="867" height="427" alt="image" src="https://github.com/user-attachments/assets/031b72fe-98d1-4acc-a514-77f16049d4b1" />

**Question 3**
---
<img width="1078" height="482" alt="image" src="https://github.com/user-attachments/assets/109d89b8-4dc3-4f12-b4f8-7bcd4bfdd34d" />

```
SELECT Address, COUNT(PatientID) AS TotalPatients
from Patients
GROUP BY Address;
```

**Output:**

<img width="923" height="477" alt="image" src="https://github.com/user-attachments/assets/12c09f89-c8bf-4fe9-bf91-bafb5bf8cc61" />

**Question 4**
---

<img width="939" height="505" alt="image" src="https://github.com/user-attachments/assets/8f0d0d50-e67e-4e60-8a11-79324f0654ee" />

```
Select count(*) as COUNT
FROM customer;
```

**Output:**

<img width="632" height="396" alt="image" src="https://github.com/user-attachments/assets/ae00d88a-558b-453b-8a5b-5531fba3363b" />

**Question 5**
---
<img width="906" height="479" alt="image" src="https://github.com/user-attachments/assets/1783f58e-effb-4494-8c0e-07c0ae96a52b" />

```
SELECT AVG(LENGTH(name)) as avg_name_length
from customer
WHERE city ='Chennai';
```

**Output:**

<img width="943" height="389" alt="image" src="https://github.com/user-attachments/assets/f9674614-ca74-4e4b-b5a6-ed03693b2282" />


**Question 6**
---
<img width="1080" height="516" alt="image" src="https://github.com/user-attachments/assets/7d3cda86-68e9-4fbd-bb71-6034af91dc36" />


```sql
select count(distinct salesman_id) as COUNT
from orders;
```

**Output:**

<img width="614" height="389" alt="image" src="https://github.com/user-attachments/assets/040f19aa-aa66-4966-bde3-5eae2216254f" />


**Question 7**
---
<img width="1039" height="505" alt="image" src="https://github.com/user-attachments/assets/c9fb7211-754f-436c-b54b-2ed706b757da" />


```
select count(customer_id) as COUNT
from customer
where grade >1;
```

**Output:**

<img width="666" height="385" alt="image" src="https://github.com/user-attachments/assets/4f46e3ec-0138-42f7-a9b3-8c9c9dbb1c48" />


**Question 8**
---
<img width="1236" height="530" alt="image" src="https://github.com/user-attachments/assets/fbd066d9-e0ae-46ee-a2ec-230c60c64da3" />


```
select age , income as Income
from employee
group by age
having min(income) < 1000000;
```

**Output:**

<img width="788" height="521" alt="image" src="https://github.com/user-attachments/assets/a804bd83-3ea8-4d07-99f5-d7989985f3cb" />


**Question 9**
---
<img width="1219" height="493" alt="image" src="https://github.com/user-attachments/assets/d5a6f7c8-54dd-4cb7-af81-21f972a19b65" />


```
select age , avg(income) AS 'AVG(income)'
from employee
group by age
having AVG(income) between 300000 and 500000;
```

**Output:**

<img width="758" height="419" alt="image" src="https://github.com/user-attachments/assets/7f925e41-c0f5-496e-bb2b-0ff8c392c120" />


**Question 10**
---
<img width="1204" height="552" alt="image" src="https://github.com/user-attachments/assets/3b833be9-9711-4ab9-b190-5494c285584b" />


```
select occupation, sum(workhour) as 'SUM(workhour)'
from employee1
group by occupation
having sum(workhour) > 20 ;
```

**Output:**

<img width="897" height="526" alt="image" src="https://github.com/user-attachments/assets/3dd81885-926a-46f8-8c37-22cdb3a0df6f" />

## Grade :

<img width="1217" height="74" alt="image" src="https://github.com/user-attachments/assets/3df67ad1-c88b-4e75-86b7-b20e306a9b61" />

## RESULT:
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
