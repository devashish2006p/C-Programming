## Introduction to Operators

Operators are **special symbols** in C that are used to **perform operations on variables or values**.

Without operators, **no calculation, no decision, no logic** is possible in a program.

### Why Operators are Important 

* **Data Manipulation**: Change and calculate values
* **Control Flow**: Used in `if`, `while`, `for` conditions
* **Efficiency**: Write short and clean code
* **Expression Evaluation**: Help build complex logic
* **Library Usage**: Used internally by many C library functions

---

## Types of Operators in C

### 1. Arithmetic Operators

Used for mathematical calculations.

| Operator | Meaning        |
| -------- | -------------- |
| +        | Addition       |
| -        | Subtraction    |
| *        | Multiplication |
| /        | Division       |
| %        | Modulus        |

Example:

```c
int sum = a + b;
```

---

### 2. Relational Operators

Used to **compare two values**.

| Operator | Meaning          |
| -------- | ---------------- |
| >        | Greater than     |
| <        | Less than        |
| >=       | Greater or equal |
| <=       | Less or equal    |
| ==       | Equal            |
| !=       | Not equal        |

Returns **1 (true)** or **0 (false)**.

---

### 3. Logical Operators

Used to combine conditions.

| Operator | Meaning     |  
| -------- | ----------- | 
| &&       | Logical AND |   
| ||       | Logical OR  |   
| !        | Logical NOT |   

Example:

```c
if(a > b && a > 0)
```

---

### 4. Bitwise Operators

Work on **binary bits**.

| Operator | Meaning     |    
| -------- | ----------- | 
| &        | AND         |    
| ||       | OR          |        
| ^        | XOR         |    
| ~        | NOT         |    
| <<       | Left Shift  |    
| >>       | Right Shift |    

Used in **low-level programming**, **OS**, **embedded**, **hacking**.

---

### 5. Assignment Operators

Assign values to variables.

| Operator | Example |
| -------- | ------- |
| =        | a = 5   |
| +=       | a += 2  |
| -=       | a -= 2  |
| *=       | a *= 2  |
| /=       | a /= 2  |

---

### 6. Increment & Decrement Operators

Increase or decrease value by 1.

| Operator | Meaning   |
| -------- | --------- |
| ++       | Increment |
| --       | Decrement |

Example:

```c
a++;
b--;
```

---

### 7. Conditional (Ternary) Operator

Short form of `if-else`.

Syntax:

```c
condition ? exp1 : exp2;
```

Example:

```c
max = (a > b) ? a : b;
```

---

### 8. Comma Operator

Executes expressions **left to right**.

Example:

```c
x = (a = 3, b = 5);
```

---

## Operator Precedence & Associativity

### Operator Precedence

Defines **which operator executes first**.

### Precedence Order (High → Low)

1. ()
2. ++ --
3. Unary + - ! ~
4. * / %
5. * -
6. < <= > >=
7. == !=
8. && ||
9. ?:
10. = += -=

---

### Associativity

Defines **direction of execution** for same precedence.

| Type       | Direction    |
| ---------- | ------------ |
| Arithmetic | Left → Right |
| Relational | Left → Right |
| Assignment | Right → Left |
| Ternary    | Right → Left |

Example:

```c
a = b = c = 5;
```

---

## Expressions in C

### What is an Expression?

A **combination of variables, constants and operators** that produces a value.

---

### Types of Expressions

| Type        | Example   |
| ----------- | --------- |
| Arithmetic  | a + b     |
| Relational  | a > b     |
| Logical     | a && b    |
| Bitwise     | a & b     |
| Conditional | a>b ? a:b |

---

### Expression Evaluation Rules

* Follow **precedence**
* Use **parentheses** for clarity

Example:

```c
5 + 10 * 2 = 25
(5 + 10) * 2 = 30
```

---

## Type Conversion

### What is Type Conversion?

Changing **one data type into another**.

---

### 1. Implicit Type Conversion

Done **automatically by compiler**.

Rules:

* `int → float` if needed
* `char → int` (ASCII)

Example:

```c
int a = 10;
float b = 5.5;
float result = a + b;
```

---

### 2. Explicit Type Conversion (Type Casting)

Done **manually by programmer**.

Syntax:

```c
(type) expression
```

Example:

```c
float x = 9.8;
int y = (int)x;
```

---

### Impact of Type Conversion

* **Loss of precision**
* **Integer division problem**

Example:

```c
int a = 9, b = 4;
float r = (float)a / b;
```

---

## Library Functions

### What are Library Functions?

Pre-defined functions provided by C.

### Common Header Files

| Header   | Use            |
| -------- | -------------- |
| stdio.h  | Input / Output |
| stdlib.h | Memory         |
| math.h   | Maths          |
| string.h | Strings        |

---

### Common Math Functions

| Function        | Use          |
| --------------- | ------------ |
| sqrt()          | Square root  |
| pow()           | Power        |
| sin(), cos()    | Trigonometry |
| log(), log10()  | Logarithm    |
| ceil(), floor() | Rounding     |

---

