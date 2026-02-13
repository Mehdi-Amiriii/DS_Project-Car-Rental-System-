🚗 Car Rental Management System
---------------------------------------------------
*Data Structures & Object-Oriented Design in C++*


📌 Table of Contents

* Project Description

* System Features

* User Roles

* System Architecture

* Data Structures Used

* Class Design Overview

* Car Status Lifecycle

* Backup & Recovery

* Compilation & Execution

* Design Principles

* Technologies

* Author

## 📖 Project Description ##

The **Car Rental Management System** is a **console-based C++ application** that simulates a real-world car rental service.

This project was designed with a strong focus on:

* **Manual implementation of data structures**

* **Object-Oriented Programming (OOP)**

* **Separation of responsibilities**

* **Realistic system workflows**

The system supports multiple user roles, reservation scheduling, car lifecycle management, and data backup.

## ✨ System Features ##

✔ User registration and authentication

✔ Role-based access control

✔ Car reservation and rental workflow

✔ Late return penalty calculation

✔ Priority-based reservation handling

✔ User blocking by manager

✔ CSV-based backup and recovery

✔ No reliance on STL containers for core logic

## 👥 User Roles

| Role | Responsibilities |
|-----|------------------|
| **Customer** | View cars, make reservations, renew rentals |
| **Staff** | Deliver cars, accept returns, apply penalties |
| **Manager** | Add cars, block users, import/export data |

Each role sees **only its own menu and permissions**.

**The RentalManager acts as the central controller coordinating all components.**

## 🧱 Data Structures Used ##
🔹 **AVL Tree**

**Purpose**: Fast car search and indexing

* Key: `car name`

* Value: `Car*`

* Time Complexity: `O(log n)`

Used for:

* Searching cars

* Preventing duplicate car names
##
🔹 Hash Table (Separate Chaining)

* Purpose: User management

* Key: `username`

* Value: `User*`

* Collision handling: Linked list chaining

Used for:

* Login

* Registration

* Blocking users



🔹 Priority Queue (Min-Heap)

**Purpose**: Reservation scheduling

Priority is determined by:

**1.** Request time

**2.** Reservation start date

Ensures:

* Fair reservation handling

* First-come-first-served behavior

##

🔹 Doubly Linked List

**Purpose**: Ordered car listing

Used to:

* Maintain insertion order

* Display all cars efficiently
##
## 🧩 Class Design Overview ##
`RentalManager`

Central system controller:

*User authentication

*Car management

*Reservation processing

*Backup & restore

##

`Car`

Represents a rental vehicle:

* Brand, price, status

* Internal reservation queue

* Tracks income and availability

##

`Reservation`

Represents a reservation request:

* Customer

* Start & end date

* Request timestamp

##

`User`

Represents a system user:

* Username

* Hashed password

* Role

* Blocked status



## 🔄 Car Status Lifecycle ##
``` scss
AVAILABLE
   ↓ reserve()
RESERVED
   ↓ deliver()
RENTED
   ↓ returnCar()
AVAILABLE or RESERVED
```

✔ Automatically updated based on reservations

✔ Ensures system consistency

##

💾 Backup & Recovery

The system supports **CSV-based backup**:

* **Export** car data to file

* **Import** car data from file

* Useful for restoring system state

Example file:
``` csv
Name,Brand,Price,Status
Camry,Toyota,80,AVAILABLE
```
##

### ⚙ Compilation & Execution ###
**Compile**:
``` bash
g++ basic_structures/*.cpp manager_system/*.cpp mainApp.cpp -o main
```

**Run**:
``` bash
./main
```

##

### 🎯 Design Principles ###

* Manual memory management

* No STL containers for core logic

* Clear separation of concerns

* Reusable, modular classes

* Academic-friendly structure

##

### 🧪 Technologies ###

* **Language**: C++

* **Paradigms**: Object-Oriented Programming

* **Concepts**:

    * AVL Trees

    * Hash Tables

    * Priority Queues

    * File I/O

    * Role-based systems

##

### 👨‍🎓 Author ###

Academic project developed to demonstrate

**advanced data structures and system design in C++**.
