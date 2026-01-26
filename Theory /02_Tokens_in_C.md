## Character Set and C Tokens

In C programming, **character set** and **tokens** are the basic building blocks of the language.

* Character set tells **which symbols** are allowed in C programs.
* Tokens are the **smallest meaningful units** that the compiler understands.

---

## C Character Set

The **C character set** includes all characters that can be used to write a C program.

### Categories of C Character Set

### 1) Letters

* Uppercase letters: A – Z
* Lowercase letters: a – z

### 2) Digits

* Numbers from 0 to 9

### 3) Special / Unique Characters

Used for operations and structure of the program.

Examples:

```
+  -  *  /  =  ;  { }  ( )  [ ]
```

### 4) Whitespace Characters

Used for formatting and readability (no effect on logic).

Examples:

* Space
* Tab
* New line

➡ These characters are used to create **keywords, variables, constants, and expressions** in C.

---

## C Tokens

**Tokens** are the smallest individual elements in a C program that have meaning to the compiler.

### Types of Tokens in C

### 1) Keywords

* Reserved words with fixed meaning
* Cannot be used as identifiers

Examples:

```
int, if, for, return, while
```

### 2) Identifiers

* Names given to variables, functions, arrays, etc.
* Used to identify program elements

Examples:

```
sum, main, _total
```

### 3) Constants

* Fixed values that do not change during execution

Examples:

```
100, 3.14, 'A', "Hello"
```

### 4) Operators

* Symbols that perform operations

Examples:

```
+  -  *  /  ==  &&  ||
```

### 5) Punctuators (Separators)

* Used to structure the program

Examples:

```
;  ,  { }  ( )  [ ]
```

### 6) Strings

* Sequence of characters inside double quotes
* Treated as a single token

Example:

```
"This is a string"
```

---

## Role of Tokens in C Code

Tokens give **meaning and structure** to a C program.

* **Keywords**: Define data types and control flow
* **Identifiers**: Make code readable by naming elements
* **Constants**: Provide fixed values for calculations
* **Operators**: Perform arithmetic and logical operations
* **Punctuators**: Organise code structure
* **Strings**: Handle and display text data

---

## Identifiers and Keywords

Identifiers and keywords are important for writing structured C programs.

* **Identifiers** → User-defined names
* **Keywords** → Reserved words of C

---

## Identifiers – Definition and Rules

### Definition

An **identifier** is a name given by the programmer to a program entity like a variable, function, array, or structure.

### Rules for Identifiers

* Must start with a **letter or underscore (_)**
* Can contain letters, digits, and underscores
* Cannot contain spaces or special symbols
* Case-sensitive (age ≠ Age)
* Cannot be a C keyword
* Should be meaningful

### Examples

**Valid Identifiers**:

```
count, _sum, numberOfStudents
```

**Invalid Identifiers**:

```
3data, price$, void
```

---

## Keywords in C

Keywords are **reserved words** with predefined meaning in C.

* Cannot be used as identifiers
* Used to define data types, control flow, storage, and structures

### Examples and Usage

* `int` → declares integer variable
* `if` → conditional statement
* `for` → loop

➡ Keywords are essential for building correct C programs.

---

## Difference Between Identifiers and Keywords

| Identifiers                      | Keywords                 |
| -------------------------------- | ------------------------ |
| User-defined                     | Predefined               |
| Can be changed                   | Cannot be changed        |
| Used to name variables/functions | Used for language syntax |

---

## Data Types and Variables

Data types and variables decide:

* What type of data is stored
* How much memory is allocated

---

## Data Types in C

### Basic Data Types

* **int** → Integer numbers (2 or 4 bytes)
* **float** → Decimal numbers (4 bytes)
* **double** → More precise decimal numbers (8 bytes)
* **char** → Single character (1 byte)

### Derived Data Types

* Arrays
* Pointers
* Structures

### Enumeration (enum)

* Used to define named integer constants

### void

* Represents no value
* Used for functions with no return value

---

## Declaring and Initialising Variables

### Declaration

```
int age;
float salary;
```

### Initialization

```
int age = 25;
float salary = 55000.50;
```

### Multiple Declaration

```
int x = 5, y = 10, z = 15;
```

➡ Proper declaration avoids runtime errors.

---

## Scope and Lifetime of Variables

### Scope

* **Local Scope** → Variables inside a function/block
* **Global Scope** → Variables outside all functions

### Lifetime

* **Automatic Variables** → Exist during function execution
* **Static Variables** → Retain value between function calls
* **Global Variables** → Exist for entire program execution

---

## Constants and Symbolic Constants

Constants are values that **do not change** during program execution.

---

## Constants in C

### Types of Constants

* Integer constants → 10, -5
* Floating constants → 3.14
* Character constants → 'A'
* String constants → "Hello"

➡ Constants improve code safety and readability.

---

## Symbolic Constants

### Using #define

```
#define PI 3.14159
```

### Using const

```
const int MAX_USERS = 100;
```

➡ `const` is better because compiler checks data type.

---

## Uses of Constants

* Mathematical values (PI)
* Limits (MAX_USERS)
* Configuration settings

---

## Using Variables and Constants Effectively

---

## Best Practices for Variables

* Use meaningful names
* Choose correct data type
* Keep scope minimal
* Always initialize variables

---

## Best Practices for Constants

* Avoid magic numbers
* Use symbolic constants
* Group related constants
* Use correct data type

Example:

```
#define MAX_BUFFER_SIZE 1024
```

---

## Example Program

```c
#include <stdio.h>
#define PI 3.14159
const int MAX_SCORE = 100;

int main() {
    int radius = 5;
    float circumference = 2 * PI * radius;
    printf("Circumference: %.2f\n", circumference);
    printf("Max Score: %d\n", MAX_SCORE);
    return 0;
}
```

---



