# Unions in C
- **Union** ek user-defined data type hai jo ek hi memory block ko multiple members ke liye share karta hai.  
- Matlab ek union ke andar jitne bhi members hote hain, sab ek hi memory location use karte hain.  
- Ek time par sirf ek member ka value valid hota hai.

## Syntax
```
union Data {
    int i;
    float f;
    char str[20];
};
```
## Breakdown
  Keyword union – batata hai ki tum ek union define kar rahe ho.
  
  Union Name (Data) – identifier jo union ko represent karta hai.
  
  Curly Braces { ... } – members define karne ke liye.
  
  Members – alag-alag data types ho sakte hain (int, float, char[]).
  
  Semicolon ; – definition ke end mein mandatory hai.

# Memory Allocation
Union ka size = largest member ka size.

Example: Agar int=4, float=4, char[20]=20, to union ka size = 20 bytes.

Sab members ek hi memory block share karte hain.

# Initialization
union Data d1 = {10};       // initialize integer
union Data d2;
d2.f = 3.14;                // assign float
strcpy(d2.str, "Hello");    // assign string
Ek time par sirf ek member ka value valid hota hai.

# Accessing Members
Dot Operator (.)
d1.i;
d2.f;

Pointer + Arrow Operator (->)
union Data *ptr = &d1;
ptr->i;

# Use Cases
  Memory Efficiency: Jab ek hi variable kabhi int, kabhi float, kabhi string store kare.
  
  Embedded Systems: Hardware registers ko represent karne ke liye.
  
  Variant Data Types: Jab ek field multiple formats mein ho sakta hai.

# Memory Allocation: Structures vs. Unions

## Structures
- Har member apna **separate memory block** occupy karta hai.
- Total size = **sum of all members** + padding (alignment ke liye).
- Matlab agar ek structure mein `int (4 bytes)`, `float (4 bytes)`, aur `char[20] (20 bytes)` hai:
  - Total size ≈ 28 bytes (padding ke saath aur bhi zyada ho sakta hai).
- **Multiple members ek saath valid hote hain** kyunki sab apna apna memory block use karte hain.

### Example
```
struct Data {
    int i;       // 4 bytes
    float f;     // 4 bytes
    char str[20];// 20 bytes
};
Total size ≈ 28 bytes (alignment ke saath 32 bhi ho sakta hai).
```
## Unions
- Sab members ek hi shared memory block use karte hain.

- Total size = largest member ka size + padding.

- Matlab agar ek union mein int (4 bytes), float (4 bytes), aur char[20] (20 bytes) hai:

- Total size = 20 bytes (largest member).

- Ek time par sirf ek member ka value valid hota hai, kyunki sab ek hi memory location share karte hain.

Example
```
union Data {
    int i;       // 4 bytes
    float f;     // 4 bytes
    char str[20];// 20 bytes
};
Total size = 20 bytes.
```
