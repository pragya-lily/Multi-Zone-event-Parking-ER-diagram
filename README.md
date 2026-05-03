# Comic-Con Parking System – ER Diagram README

##  Overview

This project represents the **database design (ER Diagram)** for a large-scale, multi-zone parking system used during events like Comic-Con India. The system is designed to efficiently manage high vehicle traffic, categorized parking, reserved spots, and complete parking sessions with payments.

It handles multiple vehicle types, special access categories (VIPs, exhibitors, cosplayers, etc.), and ensures smooth parking allocation across zones and levels.

---

##  Objectives

The ER design aims to:

* Track all vehicles entering and exiting the venue
* Manage different **vehicle categories** and **access privileges**
* Allocate parking spots dynamically based on availability and type
* Support **multi-day visits** and repeated entries
* Handle **parking sessions, tickets, and payments**
* Monitor **real-time parking availability**

---

##  Core Entities

###  Vehicle & Categories

* **VEHICLE**: Stores vehicle details like license plate, owner info, and category.
* **VEHICLE_CATEGORY**: Defines types such as bike, car, SUV, EV, etc.
* **ACCESS_CATEGORY**: Represents special access (VIP, staff, exhibitors, cosplayers).

~ One vehicle can have multiple parking sessions across different days.

---

###  Parking Infrastructure

* **PARKING_ZONE**: Represents zones and levels within the venue.
* **PARKING_SPOT**: Individual parking spaces assigned to vehicles.
* **PARKING_SPOT_CATEGORY**: Defines spot types (general, EV charging, reserved, etc.).

~ Each zone contains multiple spots, and each spot can be reused over time.

---

###  Parking Management

* **PARKING_SESSION**: Tracks entry and exit timestamps for each visit.
* **PARKING_TICKET**: Issued when a vehicle enters; linked to a session.

~ A session represents one complete parking lifecycle (entry → exit).

---

###  Payment Handling

* **PAYMENT**: Records payment details like amount, method, status, and transaction reference.

~ Each session is linked to a payment, ensuring proper fee tracking.

---

##  Relationships Summary

* A **vehicle** belongs to a **vehicle category**
* A **vehicle** may have an **access category**
* A **parking zone** contains multiple **parking spots**
* A **parking spot** belongs to a **spot category**
* A **parking session** links a vehicle to a parking spot
* A **ticket** is issued for each session
* A **payment** is made for each session

---

##  Design Highlights

* Clean separation of **sessions, tickets, and payments**
* Flexible handling of **reserved and special categories**
* Scalable for **large multi-day events**
* Avoids data redundancy through proper normalization

---

##  Conclusion

This ER diagram provides a structured and scalable foundation for building a **real-world event parking management system**. It ensures efficient tracking, allocation, and billing while supporting diverse user categories and vehicle types.

---
