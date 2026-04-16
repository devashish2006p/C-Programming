# 1. System Software
System software wo software hai jo computer hardware aur application software ke beech bridge ka kaam karta hai. Ye hardware ko control karta hai aur application software ko execute karne ke liye environment provide karta hai.

---

# 2. Types of System Software
## 2.1 Operating System (OS) 
OS ek master control program hai jo computer hardware aur software resources ko manage karta hai. 

## 2.2 Utility Software
Utility software special-purpose programs hai jo computer system ki efficiency aur maintenance improve karte hain.

## 2.3 Device Drivers 
Device driver ek special program hai jo operating system aur hardware device ka beech communication ka kaam karta hai. 

## 2.4 Language Translators 
Ye software high-level language programs ko machine language me convert karte hain taaki CPU execute kar sake.

---

# 3. User Space vs Kernel Space 
## 3.1 Kernel Space 
Kernel space wo memory area hai jahan OS kernel aur device drivers run karte hain aur jo protected hota hai, jise user programs directly access nahi kar sakte.

## 3.2 User Space 
User space wo memory area hai jahan user applications aur processes run karte hain aur jo limited access ka hota hai, jisse hardware directly access nahi kiya ja sakta.

---

# 4. System Architecture Overview
## 4.1 Definition 
System Architecture ek aisa blueprint ya design hai jo batata hai ki computer ka hardware aur software components kaise interact karte hain aur kaunse resources kaise manage hote hain.

## 4.2 Main Components of System Architecture 
1. Input Devices - Ya devices data aur instructions ko system main feed karta hai.
2. Output Devices - Ya devices processed data ko user ko dikhate hai.
3. CPU - It is a brain of computer sab calculation aur decision yahi hoti hai.
   - Components of CPU :-
     1. ALU (Arithmetic Logic Unit) - Ya calculations aur logical operations karta hai.
     2. Control Unti (CU) - Instruction fetch, decode aur execution ko control karta hai.
     3. Registers - Temporary storage for high speed processing.
5. Memory/Storage - Ishme data temporary/permanently store kia jate hai.
6. System Bus - Communication path jo CPU, memory aur I/O devices ko connect karta hai.
7. Software/System Software - OS aur system utilities hardware ko control aur manage karte hai. 

# 5. Binary Basics 
Binary ek number system hai jisme sirf do digits (0 aur 1) use hote hain, aur computer isi system ka use karke saari information (numbers, text, images, instructions) ko store aur process karta hai.

## 5.1 Bit
Bit (Binary Digit) computer ki sabse chhoti unit of information hoti hai, jisme sirf 0 ya 1 ki value hoti hai, aur isi se milkar saare data (numbers, text, images) binary form me represent hote hain.

## 5.2 MSB & LSB
MSB (Most Significant Bit) binary number ka leftmost number ko MSB kehte hai. 

LSB (Least Significant Bit) binary number ka rightost number ko LSB kehte hai. 

## 5.3 Unsigned & Signed Integers 
i) Unsigned Integers
Definition:
Stores only non-negative numbers (0 and positive).
Key Point:
No negative values exist in unsigned representation.

ii) Signed Integers
Definition:
Stores both positive and negative numbers.

Uses an extra sign bit
0 → Positive
1 → Negative
Types of Signed Number Representations
i) Sign Magnitude
Sign Magnitude is a signed number representation method where the leftmost bit represents the sign (0 for positive, 1 for negative) and the remaining bits represent the value. This method has both +0 and −0, makes arithmetic operations complex, and is not used in real computer systems.

ii) 1’s Complement
1’s Complement is a signed representation method in which a negative number is formed by inverting all bits of its positive form. It also has both +0 and −0, carry handling is complex, and therefore it is rarely used in practical systems.

iii) 2’s Complement
2’s Complement is a signed number representation method where a negative number is formed by taking the 1’s complement and then adding 1. It has only one zero, makes arithmetic simple, and is used by almost all modern CPUs.

iv) Excess (Bias) Notation
Excess (Bias) notation is a number representation technique where a fixed bias value is added to the actual number before storing it. This makes all stored values non-negative, simplifies comparison operations, and is commonly used in floating-point exponents.
## 5.4 Arithmetic operations on Signed and Unsigned
Arithmetic operations in computers are performed using binary numbers.
These operations are the foundation of all low-level programming and hardware design.

### Computers handle two types of numbers:
Unsigned numbers → Only positive values (0 and above).
Signed numbers → Both positive and negative values (using sign bit or complement methods).
### 1. Binary Arithmetic (Unsigned)
1.1 Binary Addition
Rules: 0 + 0 = 0
0 + 1 = 1
1 + 0 = 1
1 + 1 = 10 (write 0, carry 1)

Example:
1011 + 1101
11000

1.2 Binary Subtraction
Rules: 0 − 0 = 0
1 − 0 = 1
1 − 1 = 0
0 − 1 = 1 (borrow 1 from previous bit)

Example:
1010
0011
0111

1.3 Binary Multiplication
Rules: 0 × 0 = 0
0 × 1 = 0
1 × 0 = 0
1 × 1 = 1

Example:
101 ×11
1111

1.4 Binary Division
Works like decimal division but only with digits 0 and 1.
Result includes quotient and remainder.

### 2. Arithmetic with Signed Numbers
2.1 Signed Magnitude
If signs are same → add magnitudes, keep sign.
If signs differ → subtract magnitudes, keep sign of larger number.
2.2 1’s Complement
Negative numbers are formed by flipping all bits of positive number.
Addition: normal binary addition.
If carry occurs → add it back to LSB (end-around carry).
Drawback: two representations of zero (+0 and −0).
2.3 2’s Complement
Negative numbers are formed by 1’s complement + 1.
Addition/Subtraction: normal binary addition.
Overflow is ignored.
Advantage: only one zero, simpler hardware.
2.4 Excess (Bias) Notation
Store number as (actual value + bias).
Used in floating-point exponents.
Addition/Subtraction requires decode → operate → encode.
Overflow results in error/undefined.

### 3. Overflow and Underflow
3.1 Overflow
Occurs when result exceeds representable range.

Unsigned: Carry out of MSB.
Signed (2’s complement): When operands have same sign but result has opposite sign.
3.2 Underflow
Occurs when result is too small to represent.

Common in floating-point arithmetic (value close to 0).
3.3 Hardware Flags
ALU sets flags to indicate conditions:

Zero Flag (Z): Result = 0
Sign Flag (S): Result is negative
Carry Flag (C): Carry out of MSB (unsigned overflow)
Overflow Flag (O): Signed overflow
### 4. Advanced Multiplication and Division
4.1 Unsigned Multiplication
Performed using shift-add algorithm.
Result may be double the operand size.
4.2 Signed Multiplication
Operands converted to 2’s complement.
Efficient method: Booth’s Algorithm
Handles positive and negative multipliers.
Reduces number of additions/subtractions.
4.3 Division
Performed using repeated subtraction or long division.
Hardware methods:
Restoring Division Algorithm
Non-Restoring Division Algorithm
kya ya signed aur unsigned numbers ka lia enough hai?
