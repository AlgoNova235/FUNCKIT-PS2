
# Linked List Traversal & Optimal Value Selection using Digital Logic

## Overview

This project implements a hardware-based linked list traversal system using ROMs and digital ICs. The system identifies the **maximum possible value less than or equal to the current holding** and outputs:

* Selected value
* Corresponding address
* Remaining amount

---

## Approach

### Data Representation

* Linked list is stored in **ROM as an array**
* Two ROMs are used:

  * **ROM1** → Node data
  * **ROM2** → Next node address

### Traversal Strategy

* Sequential traversal using address increment
* Next node address = current address + 1
* Flip-flop used for stable address transfer

---

## Working

### 1. Linked List Traversal

* Two ROMs operate simultaneously:

  * Data output (ROM1)
  * Address output (ROM2)
* Traversal continues until **address = 255**
* Logic probe indicates completion

---

### 2. Value Selection Logic

#### Comparators Used:

* **Comparator 1:**
  Checks → Incoming value ≤ Current holding

* **Comparator 2:**
  Checks → Incoming value > Stored value

* **Comparator 3:**
  Handles dynamic updates when holding changes

---

### 3. Register Update Logic

```text
Select = (Comparator1 AND Comparator2) OR Comparator3
```

* If TRUE:

  * Register1 stores new value
  * Register2 stores corresponding address

---

### 4. Dynamic Input Handling

* User can modify input during execution
* System updates automatically
* Ensure full traversal (observe probe twice)

---

### 5. Address Storage

* Register2 stores address of selected value
* Updates only when Register1 updates

---

### 6. Remaining Amount Calculation

```text
Remaining = Current Holding − Selected Value
```

* Implemented using adders as subtractor

---

### 7. Display System

#### Binary to BCD Conversion

* Uses **Double Dabble Algorithm**
* Implemented with:

  * Adders
  * Multiplexers
  * Comparators

#### Output Display

* BCD → 7-Segment using **7448 decoder**
* Output shown on **6 displays**

---

## Hardware Implementation

* System is **8-bit**
* Built using **4-bit IC combinations**
* Modular design approach used

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c1be8bc1-166d-4fa7-9c43-0c601589dd0e" />


## Components Used

### Main Circuit

| Component   | IC Label | Quantity |
| ----------- | -------- | -------- |
| ROM         | 2732     | 2        |
| Comparator  | 7485     | 6        |
| Adder       | 74283    | 4        |
| Register    | 74179    | 4        |
| Multiplexer | 74157    | 2        |

---

### Binary to BCD Section

| Component   | IC Label | Quantity |
| ----------- | -------- | -------- |
| Comparator  | 7485     | 14       |
| Adder       | 74283    | 14       |
| Multiplexer | 74157    | 14       |
| OR Gates    | -        | 14       |

---

### Display Section

| Component                | IC Label     | Quantity |
| ------------------------ | ------------ | -------- |
| BCD to 7-Segment Decoder | 7448         | 6        |
| 7-Segment Display        | COM-CAT-BLUE | 6        |

---

### Supporting Components

| Component   | IC Label | Quantity |
| ----------- | -------- | -------- |
| Flip-Flop   | 74273    | 1        |
| AND Gate    | -        | 1        |
| OR Gates    | -        | 2        |
| NOT Gates   | -        | 9        |
| 8-input AND | 4068     | 1        |
| Clock       | D-CLOCK  | 2        |

---

## Key Features

* Hardware-based linked list traversal
* Dynamic input handling
* Optimal value selection
* Address-value synchronization
* Binary to BCD conversion
* Real-time display output

---

## Observations

* Traversal completes at **address = 255**
* System loops back to address 0
* Output stabilizes after **two full traversals**

---

## Learning Outcomes

* Implementation of data structures in hardware
* Understanding of:

  * ROM-based memory
  * Comparator logic
  * Sequential circuits
  * Number system conversion
* Modular design using 4-bit ICs

---

## Project Structure (Optional)

```text
Linked-List-Hardware-Project
 ┣ README.md
 ┣ Proteus Files
 ┣ ROM Bin Files
 ┣ Circuit Diagrams
 ┗ Documentation
```

---

If you want, I can next make this **top-tier (resume-level)** by adding:

* GitHub badges
* “How to Run” section
* Circuit diagrams + screenshots
* Crisp 2-line project pitch (very useful for interviews)
