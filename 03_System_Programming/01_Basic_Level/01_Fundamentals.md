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
4. Memory/Storage - Ishme data temporary/permanently store kia jate hai.
5. System Bus - Communication path jo CPU, memory aur I/O devices ko connect karta hai.
6. Software/System Software - OS aur system utilities hardware ko control aur manage karte hai. 

# 5. Program Execution Model 
## 5.1 Program Vs Process
- **Program**: Ya ek passive, static aur stored set of instructions hota hai jo ksi storage device par file ka form ma rehta hai aur jisme likha hota hai ki computer ko kya kaam karna hai, lekin jab tak ishe execute nhi kiya jata, tab tak ye khud kuch nhi karta.
- **Process**: Ya ek active, dynamic aur independent execution unit hota hai jo tab create hota hai jab ksi program ko OS execute karta hai aur iske pass apna alag memory space, CPU state, execution context aur system resources hote hai.

## 5.2 Compilation Process 
1. Starting Point - Is stage par hum ek .c file likhte hai jishme c code hota hai. Ushko terminal ya compiler ka command sa run karte hai.
2. Pre-processing - Is stage par **#include** ka jagha par actual function declaration paste kia jata hai. **define** ka jagha unke values ko paste kia jata hai. Conditional Compilation v yahi execute hoti hai. Aur result hota hai pure source code ko expended version milta hai aur hmare .c file ko .i ma change kar dia jata hai.
3. Compilation - Compiler pehle syntax check karta hai and pure code ko aache sa check karta hai. Agr koi error hoti hai to isi step par rok dia jata hai. Agr sub sahi hai to compiler code ko assembly language ma convert karta hai. Aur .i file ko .s ma convert kar dia jata hai.
4. Assembling - Assembly code ko convert kia jata hai binary (machine code) ma. Result hota hai object file jo CPU ke lia redable hota hai.
5. Linking - Abhi tak file ke ander likhe hue code binary ma convert ho chuka hota hai, lekin jo functions user na use kiya the wo binary ma change nahi hue hota hai, liner un fucnction ka real binary code ko system library sa fetch karta hai, aur sab mila kar ek ready to run executable file banata hai. Aur .o file ko .exe/a.out file ma change kar dia jata hai. 

 
