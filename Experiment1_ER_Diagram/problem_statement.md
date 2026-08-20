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

<img width="1085" height="887" alt="image" src="https://github.com/user-attachments/assets/1359097d-46c1-4705-8563-0b2eaf6d97c7" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|----------|
| Member | MemberID (PK), Name, Email, Age, Phone Number|Stores personal and contact details of gym members.|       
| Membership|MembershipID (PK), Name, Duration, MonthlyFee, Benefits|Stores membership plans, duration, fees, and benefits.|       
| Trainer| TrainerID (PK), Certification, Experience, phoneNumber|Stores trainer certification, experience, and contact details.|       
| Workout Schedule| ScheduleID (PK), Date, Time, Activity, Di􀆯icultyLevel|Stores scheduled workout activities, timings, and difficulty levels.|       
| Fitness Assessment| Assessment (PK), Height, Weight, Date, BMI|Stores member fitness details such as height, weight, BMI, and assessment date.|    
| Invoice| InvoiceID (PK), Date, Amount, Payment method,Payment status |Stores billing details, payment method, amount, and payment status.|

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|Member — Membership|N:1|Total on member|Many members can belong to one membership type.|
|Member — Workout Schedule|1:N|Total on workout Schedule|One member can have many workout schedules.|
|Trainer —Workout_Schedule|1:N|Total on workout schedule|One trainer can manage many workout schedules.|
|Member — Fitness Assessment|1:N|Total on Fitness Assessment|One member can have many fitness assessments.|
|Member — Invoice|1:N|Total on Invoice|One member can have many invoices.|

### Assumptions
*  Each member is enrolled in one membership plan.
*  A membership plan can be assigned to many members.
*  A trainer can conduct multiple workout schedules.

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

<img width="952" height="932" alt="image" src="https://github.com/user-attachments/assets/236e4737-ea1e-4787-a859-92d69d017049" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Library Mentor|Library mentorID (PK), Name, Email, Age, Phone Number|Stores mentor details for managing and guiding library activities.|
|Book Copy|CopyID (PK), ISBN, Edition, Availability|Stores information about individual book copies and their availability|
|Borrow record|BorrowID (PK), Issue date, Due date, Return date,Fine amount|Records book issue, due, return details, and applicable fines.|
|Cultural event|EventID (PK), Title, Date, Duration|Stores details of cultural events conducted in the library.|
|Guest Author|AuthorID (PK), Name, Nationality, Topic, Phone number|Stores information about guest authors participating in events.|
|Hall|Hall ID (PK), Name, Seating capacity, Floor, Availability|Stores hall details, seating capacity, floor, and availability.|

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|Library Member — Borrow Record|1:N|Total on Borrow record|One library member can have many borrow records.|
|Book Copy — Borrow Record|1:N|Total on Borrow record|One book copy can have many borrow records over time.|
|Library Member — Cultural Event|M:N|Partial|Many library members can attend many cultural events.|
|Cultural Event — Guest Author|1:N|Total on Guest author|One cultural event can have many guest authors.|
|Hall — Cultural Event|1:N|Total on cultural event|One hall can host many cultural events.|

### Assumptions
* A member can borrow multiple books.
* One book copy can be borrowed multiple times over time.
* Members can participate in multiple events.

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

<img width="1047" height="930" alt="image" src="https://github.com/user-attachments/assets/7714fe0c-5d35-420d-be3d-6c8b8ffa4162" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Guest   |GuestID (PK), Name, Email, Age, Phone Number|Stores the personal and contact details of restaurant guests.|
|Dining Table|TableID (PK), Table number, Capacity, Availability,Table type|Stores table number, capacity, type, and availability details.|
|Reservation|ReservationID (PK), Booking date, Booking time,Guest count, Reservation status|Stores guest booking details, timing, guest count, and reservation status.|
|Menu item|MenuItemID (PK), Item name, Price, Availability|Stores food item names, prices, and availability.|
|Staff|Sta􀆯ID (PK), Sta􀆯 Name, Role, Shift, Phone number|Stores staff details, roles, shifts, and contact information.|
|Receipt|Receipt ID (PK), Bill amount, Tax, Discount, Net amount|Stores billing details including tax, discount, and final net amount.|

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|Guest — Reservation|1:N|Total on Reservation|One guest can make multiple reservations.|
|Dining Table — Reservation|1:N|Total on reservation|One dining table can have multiple reservations over time.|
|Reservation — Menu Item|M:N|Partial|A reservation can include many menu items, and a menu item can be included in many reservations.|
|Sta􀆯 — Reservation|1:N|Total on reservation|One staff member can manage multiple reservations.|
|Reservation — Receipt|1:1|Total on receipt|Each reservation is associated with one receipt.|

### Assumptions
* One guest can make multiple reservations.
* One dining table can be reserved many times at di􀆯erent times.
* One reservation can include multiple menu items.
* One sta􀆯 member can handle multiple reservations.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
