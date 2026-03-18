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
<img width="1007" height="462" alt="510567537-1541efb4-d526-4f01-a9dd-513f1676d166" src="https://github.com/user-attachments/assets/124af0b8-434d-4ec9-84e7-e158cf403ff5" />

## Syntax:
```
CREATE TABLE item (
    item_id TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate INT NOT NULL,
    icom_id TEXT(4),
    FOREIGN KEY (icom_id) REFERENCES company (com_id)
        ON UPDATE SET NULL
        ON DELETE SET NULL
);
```
**Output:**

<img width="1246" height="253" alt="510568179-48359351-42cc-45f2-8863-d4ac5b1c4174" src="https://github.com/user-attachments/assets/143f230f-becd-4593-9d37-9ad1acfc3281" />

**Question 2**

<img width="807" height="323" alt="510568579-1d30e6fc-fa19-493d-85b0-4389b075d80f" src="https://github.com/user-attachments/assets/b90b9ec3-f6ae-4d49-8016-2de13c727d94" />

## Syntax:
```
CREATE TABLE Locations (
    LocationID INTEGER,
    LocationName TEXT,
    Address TEXT
);
```
**Output:**

<img width="1292" height="249" alt="510568864-fab7cb1c-8849-4bc2-95e7-eec65499562c" src="https://github.com/user-attachments/assets/768d0af1-b414-44e3-8abe-ab66f6b4e793" />


**Question 3**

<img width="1043" height="483" alt="510569458-a39ef5ec-50f3-46da-80ad-39aacf7dc80c" src="https://github.com/user-attachments/assets/346e3217-b682-4e14-88d7-6fa43cbfb05f" />

## Syntax:
```
INSERT INTO Student_details (RollNo, Name, Gender)
VALUES (204, 'Samuel Black', 'M');
```
**Output:**

<img width="1180" height="295" alt="510569473-4ca46aab-eb7e-47cb-a0fa-ec47d78d1ac6" src="https://github.com/user-attachments/assets/6b5f7f32-5c93-4b10-a61a-3fbb0974f8e0" />


**Question 4**

<img width="1199" height="503" alt="510569865-6c1b746c-c852-423f-9076-502cf53a7840" src="https://github.com/user-attachments/assets/5fc6ede1-d4d9-4329-a4f3-7527f4866479" />

## Syntax:
```
ALTER TABLE Companies 
ADD COLUMN designation varchar(50);

ALTER TABLE Companies 
ADD COLUMN net_salary number; 
```
**Output:**

<img width="1271" height="280" alt="510570029-3250642e-1d8b-4aa9-8088-f98edf57cbaa" src="https://github.com/user-attachments/assets/77b55cac-1a2f-4671-b20b-112cbda45dd4" />


**Question 5**

<img width="716" height="271" alt="510570147-938645fb-86cf-4488-897d-9e021889a346" src="https://github.com/user-attachments/assets/3e2da0d7-9863-4c82-a137-a2294c5afe1e" />

## Syntax:
```
CREATE TABLE Invoices(
    InvoiceID INTEGER primary key,
    InvoiceDate DATE,
    DueDate DATE,
    Amount REAL,
    CHECK (DueDate > InvoiceDate),
    CHECK (Amount > 0)
);
```
**Output:**

<img width="1173" height="187" alt="510570283-ed3e27ae-a977-4c8f-bb44-78c41caa3966" src="https://github.com/user-attachments/assets/4cdffb4b-4926-40a3-b567-4b3b54954d2a" />


**Question 6**
---
<img width="1271" height="314" alt="510570350-74a512f4-ee33-455d-a9fd-dd9b5e3b6bff" src="https://github.com/user-attachments/assets/92c895a7-b79d-4ca0-b07c-c6b260c83fe6" />

## Syntax:
```
CREATE TABLE Invoices (
    InvoiceID INTEGER primary key,
    InvoiceDate DATE,
    Amount REAL,
    DueDate DATE,  
    OrderID INTEGER  
    CHECK (Amount > 0),
    CHECK (DueDate > InvoiceDate),
    foreign key (OrderID) REFERENCES Orders(OrderID) 
);
```
**Output:**

<img width="1191" height="128" alt="510570544-cadf214b-8e2f-4faa-88ef-15ce098845eb" src="https://github.com/user-attachments/assets/13905d01-5b60-49c8-b6dd-ff3053d6c05e" />


**Question 7**
---
<img width="1305" height="279" alt="510571961-496383d7-2655-473e-8406-8b7d37f30982" src="https://github.com/user-attachments/assets/29f1c2ce-97d7-44e2-83ba-872b4fd04c5d" />

## Syntax:
```
CREATE TABLE Bonuses (
    BonusID INTEGER primary key,
    EmployeeID INTEGER,
    BonusAmount REAL,
    BonusDate DATE,
    Reason TEXT NOT NULL,
    foreign key (EmployeeID) REFERENCES Employees(EmployeeID),
    CHECK (BonusAmount > 0)
);
```
**Output:**

<img width="1349" height="147" alt="510570843-cc49f9e0-c810-4767-b54b-66446be657b0" src="https://github.com/user-attachments/assets/a8940982-91b5-4d6f-927f-546506630342" />


**Question 8**
---
<img width="1157" height="409" alt="510571241-eab21cb9-5565-44e5-b2e8-81a7d8fbec46" src="https://github.com/user-attachments/assets/df360fac-9c30-4eb5-a665-128512488f3a" />

## Syntax:
```
ALTER TABLE Student_details  
ADD COLUMN ParentsNumber number;

ALTER TABLE Student_details  
ADD COLUMN Adhar_Number number;
```
**Output:**

<img width="1274" height="291" alt="510571188-f788ac0c-1b19-4a50-b58d-b0d40130e653" src="https://github.com/user-attachments/assets/953b30c2-f3bd-4d00-992a-aeb751575795" />


**Question 9**
---
<img width="901" height="486" alt="510571314-fd917c2f-4547-4114-a3c6-e8373e0b0865" src="https://github.com/user-attachments/assets/1c93f645-31e1-42c7-aa0e-5c3a766ac11c" />

## Syntax:
```
INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
SELECT RollNo, Name, Gender, Subject, MARKS FROM Archived_students;
```
**Output:**

<img width="1237" height="206" alt="510571464-ed8f91d1-b227-44f9-a238-b36c9d5f92ab" src="https://github.com/user-attachments/assets/62a4cc23-23d1-40a4-bc8f-7d6551d55ee3" />


**Question 10**
---
<img width="1252" height="373" alt="510571516-c6f2aca3-3f60-4945-ba22-92450a25d745" src="https://github.com/user-attachments/assets/d2bd233a-19c8-431b-8860-67f1fab89f53" />

## Syntax:
```
INSERT INTO Books (ISBN, Title, Author)
VALUES ('978-1234567890', 'Introduction to AI', 'John Doe');

INSERT INTO Books (ISBN, Title, Author, Publisher, Year)
VALUES ('978-9876543210', 'Deep Learning', 'Jane Doe', 'TechPress', 2022);

INSERT INTO Books (ISBN, Title, Author, Year)
VALUES ('978-1122334455', 'Cybersecurity Essentials', 'Alice Smith', 2021);
```
**Output:**

<img width="1268" height="165" alt="510571673-300b0ced-a575-487f-bc7c-b8454cab9ff2" src="https://github.com/user-attachments/assets/af975eea-fce0-4109-afb2-b8de7b16b844" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
