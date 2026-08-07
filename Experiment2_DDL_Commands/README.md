# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--

<img width="1227" height="396" alt="Screenshot 2026-08-07 101509" src="https://github.com/user-attachments/assets/d2bf9c73-6d2f-488f-a8c8-7fb5e37294ad" />

Program :
```
CREATE TABLE Bonuses(
    BonusID INTEGER PRIMARY KEY,
    EmployeeID INTEGER ,
    BonusAmount REAL CHECK (BonusAmount > 0),
    BonusDate DATE,
    Reason TEXT NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1230" height="843" alt="Screenshot 2026-08-07 102021" src="https://github.com/user-attachments/assets/fcf62bba-43bc-455e-8559-8b48fb06e9f7" />


**Question 2**
---

<img width="1191" height="417" alt="Screenshot 2026-08-07 101802" src="https://github.com/user-attachments/assets/c7e4d144-45bb-4815-ab6f-32b1cb9c7d1f" />


```sql
CREATE TABLE Members(
    MemberID INTEGER,
    MemberName TEXT,
    JoinDate DATE
);

```

**Output:**

<img width="1223" height="852" alt="image" src="https://github.com/user-attachments/assets/0b40ef45-df2d-48ce-b9bd-18b8ca3e1b24" />


**Question 3**
---
<img width="1205" height="312" alt="image" src="https://github.com/user-attachments/assets/a3177795-d8c0-4cf8-bbc7-7cb71f5b36d3" />


```
ALTER TABLE employee ADD designation varchar(50);
```

**Output:**

<img width="1210" height="842" alt="image" src="https://github.com/user-attachments/assets/30b4e562-b2f5-437d-92c7-cd1895067de0" />


**Question 4**
---
<img width="1198" height="256" alt="image" src="https://github.com/user-attachments/assets/acc0fc5f-8808-4bc6-b132-f2e48a7e5194" />

```
INSERT INTO Products(ProductID , Name , Category,Price,Stock)
Values (101,"Laptop","Electronics",1500,50);
```

**Output:**

<img width="1222" height="802" alt="image" src="https://github.com/user-attachments/assets/bf059c9a-46b1-4eae-ae81-ddf9ff7446e6" />

**Question 5**
---
<img width="1216" height="378" alt="image" src="https://github.com/user-attachments/assets/ea3e4749-e266-4dc7-a663-ea1e769d1d75" />


```sql
CREATE TABLE Invoices (
    InvoiceID INTEGER,
    InvoiceDate DATE,
    Amount REAL CHECK (Amount > 0),
    DueDate DATE CHECK (DueDate > InvoiceDate),
    OrderID INTEGER ,
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)

);
```

**Output:**

<img width="1222" height="840" alt="image" src="https://github.com/user-attachments/assets/a8403960-4962-455a-8b09-037564ca05a0" />


**Question 6**
---
<img width="1175" height="492" alt="image" src="https://github.com/user-attachments/assets/2433a555-dbe9-41b2-a380-2ad86038b4bc" />


```
ALTER TABLE books ADD COLUMN ISBN varchar(30);
ALTER TABLE books ADD COLUMN domain_dept varchar(30);
```

**Output:**

<img width="1232" height="395" alt="image" src="https://github.com/user-attachments/assets/7c92bb98-43ac-42ae-a9c1-c30fcb6b9fcd" />


**Question 7**
---
<img width="728" height="347" alt="image" src="https://github.com/user-attachments/assets/73233919-434c-43e5-830f-92cc5c678be6" />


```
INSERT INTO Employee SELECT *FROM Former_employees;
```

**Output:**

<img width="1226" height="847" alt="image" src="https://github.com/user-attachments/assets/76a57a06-135a-4262-99bf-2b8ad87f3704" />


**Question 8**
---
<img width="1225" height="310" alt="image" src="https://github.com/user-attachments/assets/fd6e419e-8a6b-4673-9f62-1627f84d8743" />


```
CREATE TABLE ProjectAssignments (
    AssignmentID INTEGER PRIMARY KEY,
    EmployeeID INTEGER ,
    ProjectID INTEGER ,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
    
);
```

**Output:**

<img width="1230" height="842" alt="image" src="https://github.com/user-attachments/assets/7d625e77-67e3-42fd-ad06-f40f912e1e33" />


**Question 9**
---
<img width="1191" height="401" alt="image" src="https://github.com/user-attachments/assets/54d770d1-5827-4a68-a42f-e300a0d490e5" />


```
INSERT INTO Customers (CustomerID,Name,Address,City,ZipCode)
VALUES (302,"Laura Croft","456 Elm St","Seattle",98101);

INSERT INTO Customers (CustomerID,Name,Address,City,ZipCode)
VALUES (303,"Bruce Wayne","789 Oak St","Gotham",10001);
```

**Output:**

<img width="1232" height="851" alt="image" src="https://github.com/user-attachments/assets/29977fc9-af8b-43bf-b5e4-e7eb89c099b6" />


**Question 10**
---
<img width="1190" height="362" alt="image" src="https://github.com/user-attachments/assets/284e526b-a554-44a8-931f-ae95739545c2" />


```
CREATE TABLE Products(
    ProductID PRIMARY KEY,
    ProductName NOT NULL,
    Price REAL CHECK (Price > 0),
    Stock INTEGER CHECK (Stock > 0)
);
```

**Output:**

<img width="1227" height="847" alt="image" src="https://github.com/user-attachments/assets/1bf6027e-831b-4057-bbb2-89e6a3d724d6" />


**Grade:**

<img width="1388" height="136" alt="image" src="https://github.com/user-attachments/assets/ccc43888-b2ce-437f-ad09-4e996be76065" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
