# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:


<img width="1536" height="1024" alt="City fitness er" src="https://github.com/user-attachments/assets/7fd46971-4ab7-4ebd-b500-17ba7391bc8e" />


### Entities and Attributes

Entities with the corresponding Attribute:

1.Member - MemberID (PK) 
Other attribute : age,gender,address,phone, email,DOB,joinDate.

2. Membership plan - PlanID (PK)
other attribute : planName , description , Fee .

3. Trainer - TrainerID (PK)
otehr attribute : name , age, email , phone , specialization

4. Payment - PaymentID (PK)
other attributes : paymentDate , amount , ReceiptNo.


### Relationships and Constraints

| Relationship | Cardinality | Participation |
|--------------|-------------|---------------|
| Enrolls      |  N : 1      |  Partial      | 
| Attends      |  1 : 1      |  Partial      |
| Payment      |  N : N      |  Partial      |

### Assumptions
- 
- 
- 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:


<img width="1536" height="1024" alt="Book copy" src="https://github.com/user-attachments/assets/3edfaceb-bbac-4cde-b39e-0b151f2c93fb" />


### Entities and Attributes

1. Member – MemberID (PK)

Other attributes: FirstName, LastName, DateOfBirth (DOB), Gender, Phone, Email, JoinDate, Address, Age.

2. Book – BookID (PK)

Other attributes: Title, ISBN, Edition, Publisher, PublishYear, Language.

3. Book Copy – CopyID (PK)

Other attributes: Barcode, Status, ShelfLocation, AcquisitionDate.

4. Author – AuthorID (PK)

Other attributes: AuthorName, Nationality, DateOfBirth, Email.

### Relationships and Constraints

| Relationship  | Cardinality | Participation |
| ------------- | ----------- | ------------- |
| Borrows       | 1 : N       | Partial       |
| Reserves      | 1 : N       | Partial       |
| Registers_For | N : N       | Partial       |
| Has           | 1 : N       | Total         |
| Written_By    | N : 1       | Total         |
| Belongs_To    | N : 1       | Total         |


# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:


<img width="1536" height="1024" alt="RESTAURANT" src="https://github.com/user-attachments/assets/06eed925-b276-4e0b-b0dc-98a21dd845ed" />



### Entities and Attributes

1. Member – MemberID (PK)
Other attributes: FirstName, LastName, DateOfBirth (DOB), Gender, Phone, Email, JoinDate, Address, Age.

2. Book – BookID (PK)
Other attributes: Title, ISBN, Edition, Publisher, PublishYear, Language.

3. Book Copy – CopyID (PK)
Other attributes: Barcode, Status, DueDate.

4. Author – AuthorID (PK)
Other attributes: AuthorName, Nationality, DateOfBirth, Email.

5. Category – CategoryID (PK)
Other attributes: CategoryName, Description.

### Relationships and Constraints

| Relationship  | Cardinality | Participation |
| ------------- | ----------- | ------------- |
| Borrows       | 1 : N       | Partial       |
| Reserves      | 1 : N       | Partial       |
| Registers_For | N : N       | Partial       |
| Has           | 1 : N       | Total         |


### Assumptions

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
