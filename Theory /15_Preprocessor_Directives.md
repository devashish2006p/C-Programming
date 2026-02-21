# Definition 
Preprocessor directives C language ka ek special feature hain jo source code ko compile hone se pehle process karte hain. Ye compiler ka part nahi hote, balki ek alag preprocessing phase mein run karte hain. Har directive *#* symbol se start hota hai aur semicolon ki zarurat nahi hoti.

# Categories of Preprocessor Directives 

## 1. Macro Substitution 
Macro Substitution ek preprocessor directive hai jo C language mein text replacement ke liye use hota hai. Matlab, compiler se pehle preprocessor code ke andar likhe gaye macros ko unke defined values ya expressions se replace kar deta hai.

### Key Points of Macro Substitution
  1. #define ke through macro banaya jata hai.
  
  2. Ye constants aur function-like macros dono ke liye use hota hai.
  
  3. Preprocessor compile hone se pehle har jagah macro ko uske value/expression se replace kar deta hai.
  
  4. Isme semicolon nahi lagta aur ye ek line-oriented directive hota hai.

### Types of Macro Substitution
#### 1) Object-like Macros 
Ye simple macros hote hain jo ek constant value ya identifier ko represent karte hain. Preprocessor compile hone se pehle har jagah macro ko uske value se replace kar deta hai.

  - Syntax : #define MACRO_NAME value
  - Example :-
        ```
        #define PI 3.14
        #define MAX 100
        printf("Value of PI: %f\n", PI);   // Replace hoga 3.14 se
        printf("Max limit: %d\n", MAX);   // Replace hoga 100 se
        Explanation: Jab program compile hota hai to PI ko 3.14 aur MAX ko 100 se replace kar diya jata hai.
        ```
#### 2) Function-like Macros 
Ye macros ek function ki tarah behave karte hain, lekin actual function call nahi hote. Ye sirf text substitution karte hain aur arguments ko replace kar dete hain.

  - Syntax : #define MACRO_NAME(parameter) expression
  - Example :-
    ```
    #define SQUARE(x) (x * x)
    #define ADD(a, b) (a + b)
    
    printf("Square of 5: %d\n", SQUARE(5));   // Replace hoga (5 * 5)
    printf("Sum: %d\n", ADD(3, 4));           // Replace hoga (3 + 4)

    Explanation: Jab SQUARE(5) likha jata hai to preprocessor usse (5 * 5) se replace kar deta hai. Similarly, ADD(3,4) ko (3 + 4) se replace kar diya jata hai.
    ```

### Advantages of Macro Substitution
Execution speed: Macros compile hone se pehle text replacement kar dete hain, isliye function call overhead nahi hota aur program fast run karta hai.

Code reusability: Ek hi macro ko multiple jagah use kiya ja sakta hai bina bar‑bar likhe.

Flexibility: Constants aur short expressions ko easily manage karne ke liye macros helpful hote hain.

Maintainability: Agar ek macro value change karni ho to sirf ek jagah update karna padta hai, pura code automatically update ho jata hai.

### Disadvantages of Macro Substitution
Program size increase: Har jagah macro replace hone se code ka size bada ho jata hai.

No type checking: Macros sirf text replacement karte hain, type safety provide nahi karte.

Debugging difficulty: Debugging ke time macro expand ho jata hai, isliye actual error trace karna mushkil ho jata hai.

Risk of errors: Agar parentheses sahi use na kiye jaye to unexpected results aa sakte hain.

## 2. File Inclusion 
File Inclusion ek preprocessor directive hai jo C language mein ek file ke contents ko dusre file mein include karne ke liye use hota hai. Ye kaam compile hone se pehle hota hai, aur directive #include ke through likha jata hai.

### Key Points 
  1. File inclusion ka matlab hai ek file ke code ko dusre file mein laana.
  
  2. Ye mostly header files include karne ke liye use hota hai (jaise stdio.h, math.h).
  
  3. Preprocessor compile hone se pehle included file ka content copy karke program mein daal deta hai.

### Types of File Inclusion

#### 1) System Header Files 
Ye standard library ke header files hote hain jo C compiler ke saath aate hain. Inme predefined functions aur macros hote hain (jaise printf, scanf, sqrt etc.).

  Syntax : #include <filename.h>
  Example :- 
  ```
  #include <stdio.h>   // standard input-output functions
  #include <math.h>    // mathematical functions
  
  int main() {
      printf("Square root of 16 is: %f\n", sqrt(16));
      return 0;
  }

  ```
  Explanation: Yahan stdio.h aur math.h ke functions program mein use ho rahe hain. Preprocessor compile hone se pehle in files ka content program mein copy kar deta hai.

#### 2) User defined Header Files 
Ye programmer ke khud ke banaye header files hote hain jisme custom functions, macros ya constants define kiye ja sakte hain.

  Syntax : #include "filename.h"
  Example :- 
  ```
  #include <stdio.h>
  #include "myheader.h"
  
  int main() {
      greet();   // function defined in myheader.h
      return 0;
  }

  ```
  Explanation: Yahan myheader.h ek user-defined header file hai. Jab main.c compile hota hai to preprocessor myheader.h ka content copy karke program mein daal deta hai.

### Advantages of File Inclusion
  1. Code reusability: Ek hi header file ko multiple programs mein use kiya ja sakta hai.
  
  2. Modularity: Code ko alag-alag files mein divide karke manage karna easy ho jata hai.
  
  3. Maintainability: Agar ek header file update hoti hai to usse include kiye gaye sabhi programs automatically update ho jate hain.
  
  4. Standardization: System header files standard libraries provide karte hain jo reliable aur tested hote hain.

### Disadvantages of File Inclusion
  1. Program size increase: Har included file ka content program mein copy hota hai, jisse code ka size bada ho jata hai.
  
  2. Compilation time: Zyada files include karne se compilation slow ho sakta hai.
  
  3. Dependency issues: Agar user-defined header file missing ho ya galat path ho to error aata hai.
  
  4. Redundancy risk: Agar ek hi file multiple times include ho jaye to duplication aur conflicts ho sakte hain (isliye #ifndef aur #define guards use hote hain).

## 3. Conditional Compilation 
Conditional Compilation ek preprocessor feature hai jo C language mein code ke kuch hisson ko condition ke basis par compile karne ki facility deta hai. Matlab, aap decide kar sakte ho ki kaunsa part compile hoga aur kaunsa skip hoga, depending on macros ya logical conditions. Ye compile hone se pehle preprocessor ke through handle hota hai.

### Key Points 
  - Conditional compilation ka use platform-specific code, debugging code, aur release versions manage karne ke liye hota hai.
  
  - Ye directives # symbol se start hote hain aur semicolon ki zarurat nahi hoti.
  
  - Preprocessor compile hone se pehle condition check karta hai aur uske hisaab se code include/exclude karta hai.

### Types of Conditional Compilation 
#### 1. #ifdef
Definition: Agar koi macro pehle se defined hai to us block ka code compile hoga, warna skip ho jayega. Ye mostly debugging aur feature-specific code ke liye use hota hai.

  Syntax:
  #ifdef MACRO_NAME
     // code
  #endif
  
  Example:
  #define DEBUG
  #ifdef DEBUG
     printf("Debugging mode ON\n");
  #endif
  
  Explanation: Agar DEBUG defined hai to message print hoga, otherwise skip ho jayega.

2. #ifndef
Definition: Agar macro defined nahi hai to block ka code compile hoga. Ye mostly header file guards ke liye use hota hai taaki duplication na ho.

  Syntax:- 
  #ifndef MACRO_NAME
     // code
  #endif
  
  Example:
  #ifndef PI
  #define PI 3.14
  #endif
  
  Explanation: Agar PI pehle se defined nahi hai to usse define kar diya jayega.

3. #if / #else / #elif
Definition: Ye directives logical conditions ke basis par code compile karte hain. Ye zyada flexible hote hain kyunki numeric aur logical expressions evaluate kar sakte hain.

  Syntax:
  #if condition
     // code
  #elif condition
     // code
  #else
     // code
  #endif
  
  Example:
  #define VERSION 2
  #if VERSION == 1
     printf("Version 1 code\n");
  #elif VERSION == 2
     printf("Version 2 code\n");
  #else
     printf("Default code\n");
  #endif
  
  Explanation: Agar VERSION 2 hai to "Version 2 code" print hoga.

4. #endif
Definition: Ye directive conditional compilation block ko close karne ke liye use hota hai. Har #if, #ifdef, #ifndef ke saath ek #endif hona zaroori hai.

Syntax:
#ifdef MACRO_NAME
   // code
#endif

Example:
#define DEBUG
#ifdef DEBUG
   printf("Debugging mode ON\n");
#endif

Explanation: Yahan #endif block ko properly close karta hai.

### Advantages of Conditional Compilation
1. Platform-specific code: Alag-alag operating systems ya environments ke liye alag code likhna possible hota hai.

2. Debugging support: Debugging ke liye extra code add karke release version mein usse skip kar sakte hain.

3. Flexibility: Conditions ke basis par code ko include/exclude karna easy hota hai.

4. Efficiency: Unnecessary code compile nahi hota, isliye final program optimized hota hai.

### Disadvantages of Conditional Compilation
1. Code complexity: Zyada conditional directives use karne se code complicated aur hard-to-read ho jata hai.

2. Maintenance difficulty: Multiple conditions manage karna mushkil ho sakta hai, especially bade projects mein.

3. Error-prone: Agar directives galat use ho jaye to unexpected behavior aa sakta hai.

4. Portability issues: Platform-specific code zyada hone se program portable kam ho jata hai.

## 4. Compiler Control 
Compiler Control Directives C preprocessor ka ek category hai jo compiler ke behavior ko control karte hain. Matlab, ye directives compiler ko batate hain ki code ke kuch hisson ko kaise treat karna hai — jaise macros ko undefine karna, ya conditional compilation ke blocks ko manage karna. Ye compile hone se pehle preprocessor ke through execute hote hain.

### Types of Compiler Control 
#### 1. #undef 
#undef directive ka use pehle se defined macro ko remove karne ke liye hota hai. Agar aapne #define se koi macro banaya hai aur uski zarurat nahi hai, to #undef se usse cancel kar sakte ho. Ye mostly redefinition aur unnecessary macros ko avoid karne ke liye use hota hai.

  Syntax: #undef MACRO_NAME  
  Example :- 
  ```
  #define PI 3.14
  #undef PI
  
  ```
#### 2. Conditional Directives 
Conditional directives (#if, #else, #elif, #endif, #ifdef, #ifndef) ka use condition ke basis par code compile karne ke liye hota hai. Ye directives decide karte hain ki kaunsa part compile hoga aur kaunsa skip hoga. Ye debugging aur platform-specific code ke liye bahut useful hote hain.

  Syntax :- 
  #if condition
     // code
  #else
     // code
  #endif
  
  Example :- 
  ```
  #define VERSION 2
  #if VERSION == 2
     printf("Version 2 code\n");
  #endif
  ```
#### 3. #pragma 
Ya ek compiler-specific directive hai jo compiler ko special instructions deta hai. Ye implementation-dependent hota hai, yani har compiler apne hisaab se #pragma ko handle karta hai. Commonly used forms hain:

#pragma once → Header file ek hi baar include hoti hai.

#pragma pack → Structure alignment control karta hai.

#pragma warn → Compiler warnings ko enable/disable karta hai.

  Syntax : #pragma directive_name [optional_parameters]
    -> Yahan *directive_name* compiler ko diya gya instruction hota hai
    -> *optional_parameters* us instruction ka lia extra values specify karta hai
    -> Har compiler apne hisab sa alag alag programs support karta hai. 
  
  Example :- 
  ```
  #pragma once
  #include <stdio.h>
  
  void greet() {
      printf("Hello!\n");
  }
  
  ```
  
  Explanation : Ye ensure karta hai ki header file ek hi baar include ho, chahe multiple times reference kiya gaya ho.

###  Advantages of Compiler Control Directives
  1. Macro management: #undef se unnecessary macros ko remove karke redefinition aur conflicts avoid kiye ja sakte hain.
  
  2. Conditional compilation: #if, #else, #elif, #endif se platform-specific aur debugging code manage karna easy ho jata hai.
  
  3. Compiler instructions: #pragma se compiler ko special instructions diye ja sakte hain jaise header duplication avoid karna, structure alignment control karna.
  
  4. Flexibility: Ye directives program ko zyada adaptable aur efficient banate hain.

### Disadvantages of Compiler Control Directives
  1. Code complexity: Zyada conditional aur pragma directives use karne se code complicated aur hard-to-read ho jata hai.
  
  2. Portability issues: #pragma compiler-specific hota hai, isliye code har compiler par same tarike se kaam nahi karta.
  
  3. Maintenance difficulty: Multiple conditions aur pragmas manage karna bade projects mein mushkil ho sakta hai.
  
  4. Error-prone: Agar directives galat use ho jaye to unexpected behavior aur compilation errors aa sakte hain.
