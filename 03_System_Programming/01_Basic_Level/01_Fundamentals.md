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
### 1. Source File Creation 
1) User *.c* file likhta hai jisme high level c instructions hoti hai.
2) Ya file disk par stored hoti hai as plain text (ASCII/UTF-8).
### 2. Pre-processing stage
3) Compiler ka preprocessor source file ko read karta hai.
4) Sbse pehle comments remove kiye jate hai.
5) *#include* directives ko replace karke header files ka content inline paste kiya jata hai.
6) *#define* macros ko unki values sa replace kiya jata hai.
7) Function-like macros bhi expand kiye jate hai. 
8) *#undef* macros ko hata diya jata hai.
9) Conditional compilation *(#ifdef, #ifndef, #if)* evaluate hoti hai aur unnecessary code remove hota hai.
10) Header guards resolve hote hai.
11) Result ek expended source file hota hai jishe *.i* file kehte hai. 
### 3. Compilation Stage 
- **Frontend (Analysis Phase)**
- 12) Preprocessed code ko compiler frontend read karta hai.
  13) Lexical Analysis me code ko tokens ma tod diya jata hai (Keywords, identifiers, operators).
  14) Syntax Analysis (parsing) ma tokens sa parse tree/AST (Abstract Syntax Tree) bnaya jata hai.
  15) Semantic Analysis me type checking, variable declaration checking, scope resolution hota hai.
  16) Errors (Syntax/semantic) is stage par detect hote hai. 
- **Middle-end (Optimization Phase)**
- 17) AST ko intermediate representation (IR) ma convert kiya jata hai.
  18) Compiler optimizations apply karta hai.
      - Constant folding
      - dead code elimination
      - loop optimization
      - inline expansion
   19) Optimizaed IR generate hota hai. 
- **Backend (Code Generation Phase)**
- 20) IR ko target architecture ka according assembly code ma convert kiya jata hai.
  21) Register allocation hota hai (Variables ko CPU registers assign hote hai).
  22) Instruction selection hota hai (kaunsa machine instruction use hoga).
  23) Output : *.s* file ma milta hai. 
### 4. Assembling Stage
24) Assembler assembly code ko read karta hai.
25) Har assembly instruction ko corresponding machine opcode ma convert karta hai.
26) Symbole table generate hoti hai.
27) Relocation entries create hoti hai (addresses abhi final nhi hota).
28) Output ek relocatable object file (.o) hota hai. 
### 5. Linking Stage 
- **Input**
- 29) Linker Multiple Object files + libraries ko input me leta hai. 
- **Symbol Resolution**
- 30) Undefined symbols (jaisa printf()) ko resolve kiya jata hai.
  31) Libraris (static *.a* ya shared *.so*) sa required code link hota hai. 
- **Relocation**
- 32) Memory addresses assign kiya jata hai (final address binding).
  33) Code aur data section ko proper addresses milte hai. 
- **Section Merging**
- 34) Multiple object files ka sections (text, data, bss) combine kiya jata hai. 
- **Static Vs Dynamic Linking**
- 35) Static linking : Pure library code executable me copy hota hai.
  36) Dynamic Linking : Sirf reference rehta hai, runtime par laod hota hai. 
- **Output Generation**
- 37) Final executable file ban jata hai.
### 6. Executable File Internals 
38) Executable me ELF header hota hai.
39) Entry point define hota hai.
40) Sections aur segments defined hote hai.
    - *.text*
    - *.data*
    - *.bss*
41) Program headers loader ko btata hai kya load karna hai. 
### 7. Runtime Linking 
42) Agr dynamic linking hai to loader runtime par shared libraries load karta hai.
43) GOT (Global Offset Table) aur PLT (Procedure Linkage Table) use hote hai. 
### 8. Final Output
44) Ab executable fully ready hai run hone ka lia. 
