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
