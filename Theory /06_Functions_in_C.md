# Function & Function Prototype
Function: Ek named code block jo koi specific kaam karta hai; isme function ka signature aur uska actual code/body hota hai. 

Function Prototype: Ek declaration jo compiler ko function ka naam, return type, aur parameter types batata hai; isme function ki body nahi hoti.

# Syntax of Function 
```
return_type function_name(parameter_list) {
    // function body
}
```
## Breakdown 
    Return type — kya value wapas milegi (int, float, void).
    
    Function name — valid identifier jo function ko pehchaan dega.
    
    Parameter list — comma-separated inputs with types (agar koi nahi to void ya empty ()).
    
    Function body — {} ke andar wala actual code jo kaam karta hai.

# Prototype vs Definition 
Prototype: Sirf declaration; compiler ko batata hai function ka naam, return type, aur parameter types. Example: int add(int a, int b);

Definition: Actual implementation with body. Example: int add(int a, int b) { return a + b; }

# Role of Function Declaration(Prototype) 
    Compiler ko inform karta hai: Jab function ka use main() se pehle hota hai, declaration compiler ko batata hai ki aisa function exist karega.
    
    Error checking: Agar function call mein galat type ya number of arguments diye gaye ho, compiler error/warning dega.
    
    Code organization: Bade programs mein functions alag-alag files mein hote hain; declaration/prototype unhe modular aur maintainable banata hai.
    
    Flexibility: Function ko call karne se pehle uski definition likhna zaroori nahi hota, bas prototype hona chahiye.

# Best Practices for Function Prototyping 

    Always declare prototypes before main()  
    Taaki compiler ko pata ho function exist karta hai aur usko call karne se pehle error na aaye.
    
    Prototype aur definition exact match honi chahiye  
    Return type, function name, aur parameter types dono mein same hone chahiye.
    
    Use void for no parameters  
    Agar function koi argument nahi leta to int func(void); likho, int func(); avoid karo.
    
    Group prototypes in header files  
    Bade projects mein prototypes ko .h files mein rakho aur .c files mein include karo. Ye modular aur maintainable hota hai.
    
    Avoid redundant prototypes  
    Ek hi function ka prototype baar-baar likhne se code clutter hota hai.
    
    Add comments/documentation  
    Prototype ke saath short comment likho jo bataye function kya karta hai, inputs aur outputs kya hain.

# Core categories of Function 
1. Standard Library Functions - Ya wo functions hote hai jo C ka standard library (jaisa <stdio.h>, <math.h>) mein pehle sa likhe hote hai. Ya common tasks ka lia ready made soluctions provide karta hai, jaisa input/output, string handling, match operation etc. Ya functions highly optimized aur portable hote hai isiliye programmer ko khud sa basic operations likhne ki zarurat nahi hoti. Ya C ka runtime enviroment ka essential part hai.
2. User defined functions - Ye functions programmer khud likhta hai apne specific requirement ke liye. Code ko modular, reusable aur readable banate hain. Large programs ko chhote manageable blocks mein todne ke liye use hote hain.
3. Recursive Functions - Aise functions jo apne aapko call karte hain directly ya indirectly. Complex problems ko chhote sub-problems mein todne ke liye use hote hain (divide-and-conquer approach).

# Built-in functions vs User defined functions 
    Built-in Functions: Ye C ke standard library ka part hote hain. Compiler aur runtime environment inhe already support karte hain. Inka fayda hai ki ye optimized aur portable hote hain, aur programmer ko basic operations khud likhne ki zarurat nahi hoti. Example: printf() ek complex formatted output function hai jo internally bahut saari cheeze handle karta hai.
    
    User-Defined Functions: Ye programmer ke control mein hote hain. Jab built-in functions se requirement puri nahi hoti, tab user apne functions likhta hai. Ye code ko modular banate hain, reusability badhate hain, aur readability improve karte hain. Example: Agar tumhe ek custom tax calculation karna hai jo standard library mein nahi hai, to tum apna function likhoge.

# Passing Arguments to Functions 
When we call a function, we may want to pass information (arguments) to it.
There are two main ways to pass arguments: 
1. Call by value
Jab function ko arguments pass kiye jaate hain, to unki copy function ke parameters mein store hoti hai. Function ke andar changes sirf copy par hote hain, original variable par koi effect nahi hota.
    Ex :-
```
void change(int x) {
x = 10;   // sirf copy change hogi
}

int main() {
    int a = 5;
    change(a);
    printf("%d", a);  // Output: 5 (original unchanged)
    return 0;
}

```
2. Call by Reference
Jab function ko arguments ke address (pointer) pass kiye jaate hain, to function directly original variable par kaam karta hai. Function ke andar changes original variable par reflect hote hain.
    Ex :-
```
void change(int *x) {
    *x = 10;   // original variable change hoga
}

int main() {
    int a = 5;
    change(&a);
    printf("%d", a);  // Output: 10 (original changed)
    return 0;
}

```
             
# Nested Function 
Nested function ka matlab hota hai ek function ko doosre function ke andar define karna.
Standard C (ANSI C) mein nested functions allowed nahi hote. Matlab tum ek function ke andar doosra function define nahi kar sakte. Agar try karoge to compiler error dega.

## Nested Functions – When and Why to Use

### 1. Modularity
Agar ek task sirf ek specific function ke liye relevant hai, to usse nested function ke andar rakhna code ko **cleaner aur manageable** banata hai.  
➡ Example: Ek helper calculation jo sirf ek outer function ke andar hi use hoti hai.

### 2. Encapsulation
Jab ek function sirf ek outer function ke scope mein hi zaroori hai, to usse nested karne se wo **baaki program ke liye expose nahi hota**.  
➡ Isse unnecessary global clutter avoid hota hai.

### 3. Local Scope
Agar tumhe ek calculation ya operation sirf ek outer function ke context mein karna hai, to nested function use karna logical hota hai.  
➡ Ye ensure karta hai ki wo logic sirf usi outer function ke andar accessible ho.

# Recursion

Ek recursive function wo hota hai jo apne aapko directly ya indirectly call karta hai, 
aur problem ko chhote parts mein todta hai jab tak base case reach na ho jaaye.  
Ye approach complex problems ko simplify karne ke liye use hoti hai.

## Base Case and Recursive Case in Recursive Functions

- **Base Case**: Ye wo condition hoti hai jahan recursion stop ho jaata hai.  
  Isse infinite recursion aur stack overflow prevent hota hai.  

- **Recursive Case**: Ye wo part hota hai jahan function apne aapko call karta hai 
  ek simpler form ke saath, taaki problem gradually solve ho.  

---

## Types of Recursion

- **Direct Recursion**: Jab ek function apne aapko directly call karta hai.  

- **Indirect Recursion**: Jab ek function doosre function ko call karta hai, 
  aur wo function phir se pehle function ko call karta hai.  
  Ye thoda complex recursion scenario create karta hai.  

---

## Common Pitfalls in Recursive Functions

1. **Missing Base Case**  
   Agar base case define nahi kiya gaya to recursion kabhi stop nahi hoga → infinite loop aur stack overflow ho sakta hai.  

2. **Too Many Function Calls**  
   Recursive solution kabhi-kabhi unnecessary zyada calls generate karta hai, jo performance aur memory ko affect karta hai.  

3. **Hard to Debug**  
   Recursive flow trace karna mushkil hota hai kyunki function repeatedly apne aapko call karta hai aur execution path complex ho jaata hai.  

## How Functions Are Used for Modularizing Programs

Functions program ko **chhote manageable parts** mein tod dete hain, jisse code easy to samajhna aur maintain karna ho jaata hai.  

Functions se **reusability aur readability** improve hoti hai, kyunki ek baar likha hua function baar-baar use kiya ja sakta hai bina code repeat kiye.  




