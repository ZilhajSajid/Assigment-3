# ⚽ Football Ticket Booking System - Database Design & SQL Queries

## 📌 Overview

This project is a **relational database design and SQL practice assignment** for a simplified Football Ticket Booking System.  
It demonstrates database modeling, relationships (ERD), and intermediate to advanced SQL query writing.

The system manages:

- Football fans (users)
- Football matches (events)
- Ticket bookings (transactions)

---

## 🎯 Objectives

By completing this project, I have learned to:

- Design an ERD with **1-to-1, 1-to-Many, and Many-to-1 relationships**
- Define **primary keys and foreign keys**
- Maintain **referential integrity**
- Write **complex SQL queries** using:
  - JOINs (INNER, LEFT)
  - Subqueries
  - Aggregations
  - NULL handling (COALESCE, IS NULL)
  - Pattern matching (LIKE / ILIKE)
  - Pagination and filtering

---

## 🧱 Database Schema

### 1. Users Table

Stores all system users (fans and ticket managers).

| Field        | Type     | Description                   |
| ------------ | -------- | ----------------------------- |
| user_id      | INT (PK) | Unique user identifier        |
| full_name    | VARCHAR  | Full name of user             |
| email        | VARCHAR  | Email (unique login)          |
| role         | VARCHAR  | Ticket Manager / Football Fan |
| phone_number | VARCHAR  | Contact number                |

---

### 2. Matches Table

Stores football match details.

| Field               | Type     | Description               |
| ------------------- | -------- | ------------------------- |
| match_id            | INT (PK) | Unique match ID           |
| fixture             | TEXT     | Teams playing             |
| tournament_category | TEXT     | League or tournament name |
| base_ticket_price   | DECIMAL  | Base ticket price         |
| match_status        | TEXT     | Availability status       |

---

### 3. Bookings Table

Stores ticket booking transactions.

| Field          | Type     | Description        |
| -------------- | -------- | ------------------ |
| booking_id     | INT (PK) | Unique booking ID  |
| user_id        | INT (FK) | References Users   |
| match_id       | INT (FK) | References Matches |
| seat_number    | TEXT     | Seat allocation    |
| payment_status | TEXT     | Payment state      |
| total_cost     | DECIMAL  | Final ticket cost  |

---

## 🔗 Relationships (ERD Summary)

- **Users → Bookings** (1-to-Many)
- **Matches → Bookings** (1-to-Many)
- **Bookings → Users & Matches** (Many-to-1)

Each booking represents:

> One user booking one seat for one match.

---

## 🧾 Sample Features Implemented

- NULL handling using `COALESCE`
- Case-insensitive search using `ILIKE`
- Aggregation with `AVG()`
- Filtering with subqueries
- JOIN operations (INNER + LEFT JOIN)
- Sorting and pagination using `ORDER BY`, `LIMIT`, `OFFSET`

---

## 🧪 SQL Query Highlights

### Query 1: Champions League Matches

Find available Champions League matches.

### Query 2: Search Users

Find users by name pattern (`Tanvir`, `Haque`) using `ILIKE`.

### Query 3: Pending Payments

Show bookings with missing payment status using `COALESCE`.

### Query 4: Booking Details

Join Users, Bookings, and Matches tables.

### Query 5: All Users + Bookings

Use LEFT JOIN to include users with no bookings.

### Query 6: Above Average Spending

Find bookings with cost higher than average.

### Query 7: Top Expensive Matches

Get 2nd and 3rd highest priced matches using LIMIT/OFFSET.

---

## 🛠️ Technologies Used

- PostgreSQL / MySQL
- SQL (DDL + DML + DQL)
- ERD Design Tools (Draw.io / Lucidchart)

---

## 📊 ERD Diagram

👉 https://drive.google.com/file/d/1RdSKE2mP9IkPhUzz8GK_AfuaZpE8ltdz/view?usp=sharing


---

## 🚀 Learning Outcome

This project improved my understanding of:

- Relational database design
- Real-world data modeling
- SQL query optimization
- Handling NULL values and joins
- Analytical thinking with SQL

---

## 👨‍💻 Author

**Md. Zilhaj Un Noor**  
Aspiring Full Stack Web Developer