# 📚 Library Management System Database

This project implements a **relational database schema** for a **Library Management System** using **MySQL**.  
It models real-world operations such as managing members, books, loans, reservations, fines, and staff.  

---

## 🚀 Features of the Database
- Store **members’ information** (name, contact details, address).  
- Manage **books**, including **categories** and **publishers**.  
- Record **loans** when members borrow books.  
- Track **reservations** for books requested by members.  
- Keep information about **staff** who manage the library.  
- Apply **fines** for overdue book returns.  
- Define **relationships** between entities using **foreign keys**.  

---

## 🛠️ Database Structure

### 1. **Members**
Stores details of library members.  
**Columns**: MemberID, FirstName, LastName, Email, Phone, Address  

### 2. **Books**
Stores details of all books in the library.  
**Columns**: BookID, Title, Author, ISBN, PublishedYear, CategoryID, PublisherID  

### 3. **Categories**
Defines book categories (e.g., Fiction, Science, History).  
**Columns**: CategoryID, CategoryName  

### 4. **Publishers**
Stores information about publishers.  
**Columns**: PublisherID, PublisherName, Contact, Address  

### 5. **Loans**
Tracks which member borrowed which book and the loan/return dates.  
**Columns**: LoanID, MemberID, BookID, LoanDate, ReturnDate  

### 6. **Reservations**
Stores details of book reservations made by members.  
**Columns**: ReservationID, MemberID, BookID, ReservationDate  

### 7. **Staff**
Stores information about library staff.  
**Columns**: StaffID, FirstName, LastName, Role, Email  

### 8. **Fines**
Keeps records of fines for overdue book returns.  
**Columns**: FineID, LoanID, Amount, PaidStatus  

---

## 🔑 Relationships Between Tables
- **Members → Loans** (One-to-Many): A member can borrow many books.  
- **Members → Reservations** (One-to-Many): A member can reserve multiple books.  
- **Books → Loans** (One-to-Many): A book can be borrowed multiple times.  
- **Books → Reservations** (One-to-Many): A book can be reserved by multiple members.  
- **Books → Categories** (Many-to-One): Each book belongs to one category.  
- **Books → Publishers** (Many-to-One): Each book is published by one publisher.  
- **Loans → Fines** (One-to-One): Each loan may have a fine.  

---

## 📂 File Contents
The `.sql` script includes:
1. `CREATE DATABASE` statement  
2. `CREATE TABLE` statements for all entities  
3. **Primary Keys**, **Foreign Keys**, and **Constraints**  

---

## ✅ How to Use
1. Copy the script into a file named `librarydb.sql`.  
2. Open MySQL and run:  
   ```sql
   SOURCE path/to/librarydb.sql;
