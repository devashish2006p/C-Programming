# Definition 
Storage Classes in C ekdum fundamental concept hai jo batata hai ki ek variable ka scope (visibility), lifetime (kitni der tak exist karega), aur memory location kya hoga. Matlab, storage class decide karta hai ki ek variable program ke andar kahan accessible hoga aur uski value kitni der tak retain hogi.

# There are four types of Storage Classes in C

## Autometic Veriables 
*auto* keyword btata hai ki veriable autometic type ka hai. Ya veriables function ke ander declare hota hai aur function ka khatam hote he distroy ho jate ha. 
### Default Behaviour :- 
- Scope : Local (sirf us block/function ke andar jahan declare kiya gaya hai). - Variable bahar access nahi ho sakta.
- Lifetime : Sirf us block/function ke andar jab tak execution chal raha hai. Block khatam hote hi variable destroy ho jaata hai.
- Default value : Garbage (undefined)
- Memory Location : RAM (stack segment)
- keyword : auto

## External Veriables 
extern ka use ksi veriable ko dushre file/function sa link karne ka lia hota hai. Ya btata hai ke veriable kahi aur define hai, yaha sirf ushka sirf ushka reference use karna hai. 
### Default Behaviour 
- Scope : Global (poore program ke across, multiple files mein). - Variable ek file mein define hota hai aur dusre file mein `extern` keyword ke saath accessible hota hai.
- Lifetime : Poore program ke duration tak. Ek file mein define kiya gaya variable dusre files mein accessible hota hai.
- Default : 0
- Memory Location : RAM (global/static storage area).
- Keyword : extern
*extern sirf veriable ko reference deta hai, define nahi akrta. Agr aap same file ma *extern int a;* likh do bina define kia to error milega jab tak aap a ko kahi define nahi karte*

## Static Storage Class
static keyword ka use ksi veriable ko permanent memory dene ka lia hota hai. Local scope ka bawjood veriable destroy nahi hota, balki ushki value function ka bahar v preserve rehti hai. 
### Default Behaviour 
- Scope : Local agar function ke andar declare kiya ho, to sirf us function ke andar accessible hai. - Global agar function ke bahar declare kiya ho, to sirf us file ke andar accessible hai (file scope).
- Lifetime : Poore program ke duration tak. Value retain hoti hai across multiple function calls.
- default value : 0
- Memory Location : RAM (data segment → static storage area).
- Keyword : static

## Register storage class 
register keyword suggest karta hai compiler ko veriable ke RAM ma nahi balki CPU register me rakho for faster access. Ishka use high speed veriable jaisa loop counter ka lia hota hai. 
### Default Behaviour 
- Scope : Local (sirf us block/function ke andar). - Bahar se access nahi ho sakta, aur address-of operator (`&`) use nahi kar sakte.
- Lifetime : Sirf us block/function ke andar jab tak execution chal raha hai. Block khatam hote hi variable destroy ho jaata hai.
- default value : garbage
- Memory location : CPU register (agar available ho), otherwise RAM (stack).
- keyword : register 

# Memory Allocation for Storage Classes in C

##  1. Stack Allocation (auto & register variables)
- **auto** aur **register** variables ke liye memory **stack segment** mein allocate hoti hai.
- Stack ek memory region hai jo **function calls aur local variables** ke liye use hota hai.
- Jab function call hota hai to stack grow karta hai, aur jab function return hota hai to stack shrink ho jaata hai.
- Isliye memory automatically free ho jaati hai jab function exit karta hai.
- **register** variables ideally CPU register mein store hote hain (fast access ke liye), lekin agar register available na ho to stack mein allocate hote hain.

### Example
```
void function() {
    auto int x = 10;      // Allocated on stack, destroyed when function exits
    register int y = 20;  // Stored in CPU register (if available), else stack
}
```
## 2. Data Segment Allocation (static & extern variables)
- static aur extern variables ke liye memory data segment mein allocate hoti hai.
- Data segment ek memory region hai jo poore program ke runtime tak valid rehta hai.
- Ye memory stack ki tarah expand/shrink nahi hoti.
- Variables ek hi baar initialize hote hain aur apni value retain karte hain jab tak program chal raha hai.
- static → scope local ho sakta hai, lekin lifetime poore program tak hoti hai.
- extern → global variables jo multiple files mein accessible hote hain.

Example
```
static int x = 5;   // Allocated in data segment, survives multiple function calls
extern int y;       // Declared in one file, defined in another, stored in data segment
```


