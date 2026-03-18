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

<img width="1311" height="902" alt="548036876-7cf7da6b-cb6d-41b9-975d-c72d83a9b3fd" src="https://github.com/user-attachments/assets/69d6d16a-d7bd-40e5-bb47-e37e02af45e0" />


### Entities and Attributes

<img width="1119" height="306" alt="image" src="https://github.com/user-attachments/assets/76016a7f-00db-4752-88a3-7a3e313f021e" />


### Relationships and Constraints

<img width="1298" height="437" alt="image" src="https://github.com/user-attachments/assets/942064e3-dabd-451a-aa9c-d180f642133f" />


### Assumptions
1.Each member, trainer, and program has a unique ID.

2.A member can join multiple programs, but not the same program twice at the same time.

3.A program can have multiple trainers.

4.Members can book personal training sessions with trainers in advance.

5.Attendance is recorded for each session.

6.Payments are recorded separately for memberships and personal training sessions.

7.Expired members cannot book new sessions.

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

<img width="1332" height="911" alt="image" src="https://github.com/user-attachments/assets/356dd1c5-f33e-45fe-87ea-49c4f1d6d139" />


### Entities and Attributes

<img width="1163" height="397" alt="image" src="https://github.com/user-attachments/assets/16646b82-1d7e-4c71-8413-74de9601b36f" />


### Relationships and Constraints

<img width="1289" height="365" alt="image" src="https://github.com/user-attachments/assets/67c17574-279f-42e7-96e5-084030e555d1" />

### Assumptions
1.Each member, book, event, speaker, and room has a unique ID.

2.A member can borrow multiple books, but a book can be issued to only one member at a time.

3.Loan date and return date are recorded for every borrowed book.

4.Fine is calculated based on the number of overdue days.

5.A member can register for multiple events.

6.An event can have multiple speakers/authors.

7.A room can be booked for events or study, but only one booking per time slot.

8.A book belongs to only one category.

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

<img width="961" height="1291" alt="548038403-22ca5492-9121-49fe-9620-046b2e574a3a" src="https://github.com/user-attachments/assets/ecbe0173-4434-47cc-b5f7-4fba2907bede" />

### Entities and Attributes

<img width="1084" height="430" alt="image" src="https://github.com/user-attachments/assets/5741ee10-f5e6-40a4-9eaf-fb04d208e053" />

### Relationships and Constraints

<img width="1248" height="333" alt="image" src="https://github.com/user-attachments/assets/24a196b1-64bc-4d26-af5e-cf1794ba266d" />


### Assumptions
1.Each customer, reservation, waiter, dish, and bill has a unique ID.

2.A reservation is made for a specific date and time with a fixed number of guests.

3.Walk-in customers are also recorded as reservations.

4.One reservation is assigned to one waiter, but a waiter can handle multiple reservations.

5.Each order is linked to one reservation.

6.An order can contain multiple dishes, and each dish belongs to one category.

7.Only one final bill is generated per reservation.

8.The bill includes food charges + service charges.


## RESULT
Thus the ER Diagram for each scenario has been drawn and explained successfully.
