# Software Engineering – Chapter 8: System Modeling



Prepared by: \[ٍEmran Mirzad]
For: Kabul University – Software Engineering
Topic: UML Modeling – Chapter 8

---

## ✅ Assignment 1: List Five UML Diagrams

### 1. **Use Case Diagram**

* **Purpose**: Represents system-user interactions.
* **Example**: (Login), (Checkout), (Search Product).

### 2. **Class Diagram**

* **Purpose**: Shows structure of classes.
* **Example**: Student class with attributes and methods.

### 3. **Sequence Diagram**

* **Purpose**: Displays sequence of message exchange.
* **Example**: Login flow: User → System → DB → Result.

### 4. **Activity Diagram**

* **Purpose**: Describes workflows.
* **Example**: Booking a flight step-by-step.

### 5. **State Diagram**

* **Purpose**: Shows object states and transitions.
* **Example**: Order → Paid → Shipped → Delivered.

---

## ✅ Assignment 2: Use Case Diagram – Include & Extend

### System: Flight Booking System

**Actors:** Passenger, Payment System
**Use Cases:** Search Flights, Book Flight, Make Payment, Apply Promo Code, Send Confirmation Email

```plaintext
Passenger --> (Search Flights)
Passenger --> (Book Flight)
(Book Flight) --> <<include>> (Make Payment)
(Book Flight) --> <<extend>> (Apply Promo Code)
(Make Payment) --> <<include>> (Send Confirmation Email)
```

---

## ✅ Assignment 3: Class Diagram – School Management System

### Classes and Key Features:

* **Student**: id, name, grade → register(), viewCourses()
* **Teacher**: id, name, subject → assignCourse(), gradeStudent()
* **Course**: code, title, credits → addStudent(), removeStudent()
* **Classroom**: number, capacity → scheduleClass()
* **School**: name, address → addStudent(), hireTeacher()

### Relationships:

* Student ⬌ Course (many-to-many)
* Teacher → Course (one-to-many)
* Course → Classroom (one-to-one)
* School → Student/Teacher (aggregation)

---

## ✅ Assignment 4: State Diagram – Online Order System

### States:

* **Order Created**
* **Paid**
* **Processing**
* **Shipped**
* **Delivered**
* **Cancelled** (can happen before Shipped)

### Transitions:

* `pay()` → Order Created → Paid
* `prepareOrder()` → Paid → Processing
* `ship()` → Processing → Shipped
* `deliver()` → Shipped → Delivered
* `cancel()` → at any point before shipping

```plaintext
[Order Created]
     |
   pay()
     ↓
    [Paid]
     |
prepareOrder()
     ↓
[Processing]
     |
   ship()
     ↓
  [Shipped]
     |
 deliver()
     ↓
[Delivered]

(cancel() → from any state before "Shipped" → [Cancelled])
```




