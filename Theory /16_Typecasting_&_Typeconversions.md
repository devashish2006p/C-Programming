# Type Conversion (Implicit Conversion)
Jab compiler khud automatically ek data type ko dusre data type me convert karta hai, usko type conversion bolte hain.

## Example 
int a = 10;
float b = a;   // int → float (automatic)

- Yaha kya hua?
  - a ka type = int
  - b ka type = float
- Compiler ne automatically 10 ko 10.0 bana diya
- Programmer ne manually kuch nahi kiya.
- Compiler ne khud convert kiya.

# Type Casting (Explicit Conversion)
Jab programmer khud force karke data type change karta hai, usko type casting bolte hain.
Isko explicit conversion bhi bolte hain.

## Syntax
(type) variable

## Example 
float a = 5.8;
int b = (int) a;
- Yaha:
  - (int) → type casting hai
  - 5.8 → 5 ban gaya (decimal part remove ho gaya)
- Ye programmer ne manually force kiya.
