
# Half Adder and Full Adder Using Logisim Evolution

## Overview

This project demonstrates the design and simulation of two fundamental combinational logic circuits using **Logisim Evolution**:

1. **Half Adder**
2. **Full Adder**

These circuits are essential building blocks in **digital electronics** and are used in arithmetic logic units (ALUs), processors, and digital systems for performing binary addition.

The project involves constructing the circuits using basic logic gates, verifying their truth tables, and observing the outputs through simulation.

---

# Requirements

## Software

* Logisim Evolution (recommended version 3.x or later)

Download from the official repository:
https://github.com/logisim-evolution/logisim-evolution

## Basic Knowledge

* Binary numbers
* Logic gates (AND, OR, XOR)
* Truth tables
* Combinational logic circuits

---

# Project Structure

```
adder-project/
│
├── half_adder.circ
├── full_adder.circ
└── README.md
```

---

# 1. Half Adder

## Description

A **Half Adder** adds two single-bit binary numbers and produces two outputs:

* **Sum (S)**
* **Carry (C)**

### Inputs

* A
* B

### Outputs

* S (Sum)
* C (Carry)

---

## Truth Table

| A | B | Sum (S) | Carry (C) |
| - | - | ------- | --------- |
| 0 | 0 | 0       | 0         |
| 0 | 1 | 1       | 0         |
| 1 | 0 | 1       | 0         |
| 1 | 1 | 0       | 1         |

---

## Boolean Expressions

```
Sum = A XOR B
Carry = A AND B
```

---

## Building the Half Adder in Logisim Evolution

### Step 1: Create a New Circuit

1. Open **Logisim Evolution**
2. Click **File → New**

---

### Step 2: Add Input Pins

From the **Wiring** library:

Add two **Input Pins**

* Label them **A** and **B**

Set:

* Data Bits = 1
* Facing = East

---

### Step 3: Add Logic Gates

From the **Gates** library:

Add:

* **1 XOR Gate**
* **1 AND Gate**

---

### Step 4: Connect Inputs

Connect:

```
A ─┬─> XOR
   │
   └─> AND

B ─┬─> XOR
   │
   └─> AND
```

---

### Step 5: Add Output Pins

Add two **Output Pins**:

Label them:

* **S** (Sum)
* **C** (Carry)

Connections:

```
XOR output → S
AND output → C
```

---

### Step 6: Test the Circuit

Toggle the inputs and confirm the outputs follow the truth table.

---

# 2. Full Adder

## Description

A **Full Adder** adds **three binary inputs**:

* A
* B
* Carry Input (Cin)

It produces:

* **Sum (S)**
* **Carry Output (Cout)**

---

## Inputs

* A
* B
* Cin

---

## Outputs

* S (Sum)
* Cout (Carry Out)

---

## Truth Table

| A | B | Cin | Sum | Cout |
| - | - | --- | --- | ---- |
| 0 | 0 | 0   | 0   | 0    |
| 0 | 1 | 0   | 1   | 0    |
| 1 | 0 | 0   | 1   | 0    |
| 1 | 1 | 0   | 0   | 1    |
| 0 | 0 | 1   | 1   | 0    |
| 0 | 1 | 1   | 0   | 1    |
| 1 | 0 | 1   | 0   | 1    |
| 1 | 1 | 1   | 1   | 1    |

---

## Boolean Expressions

```
Sum = A XOR B XOR Cin
Cout = (A AND B) OR (Cin AND (A XOR B))
```

---

# Building the Full Adder in Logisim Evolution

## Method 1: Using Two Half Adders (Recommended)

A full adder can be constructed using:

* **2 Half Adders**
* **1 OR Gate**

---

### Step 1: First Half Adder

Inputs:

```
A, B
```

Outputs:

```
S1 = A XOR B
C1 = A AND B
```

---

### Step 2: Second Half Adder

Inputs:

```
S1, Cin
```

Outputs:

```
Sum = S1 XOR Cin
C2 = S1 AND Cin
```

---

### Step 3: Carry Output

Combine carry signals:

```
Cout = C1 OR C2
```

---

## Logic Layout

```
        A --------\
                   XOR ---- S1 ----\
        B --------/                 XOR ---- SUM
                                      /
        Cin --------------------------/

        A ---- AND ---- C1 ----\
                                 OR ---- Cout
S1 ---- AND ---- C2 ------------/
```

---

# Testing the Full Adder

1. Toggle **A**
2. Toggle **B**
3. Toggle **Cin**

Verify outputs against the truth table.

---

# Applications

Adders are widely used in:

* CPU arithmetic units
* Binary counters
* Digital signal processors
* Microcontrollers
* Embedded systems

Full adders are chained together to form:

* **Ripple Carry Adders**
* **Parallel Adders**
* **Arithmetic Logic Units**

---

# Possible Extensions

To extend this project, you can implement:

* **4-bit Ripple Carry Adder**
* **8-bit Binary Adder**
* **Subtractor using 2's complement**
* **Arithmetic Logic Unit (ALU)**

---

# Author

Kilavi Musyoki  
Telecommunications and Information Engineering

---

# License

This project is open for academic and educational use.
