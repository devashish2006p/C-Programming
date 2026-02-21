# Definition 
Pointer is a veriable that stores the memory address of another veriable. Normal veriable sirf data store karta hai but pointter veriable srif address store karta hai normal veribales ka. 

# Pointer Declaration 
Syntax : data_type *pointer name; 
Example :- 
```
int *p;
float *r;
```

# Pointer Initialization 
Pointer veriable ko ksi valid address sa initialize karna cahiya otherwise wo wild pointer ban jata hai. 
Example :- 
```
int a = 5;
int *p = &a // Initialized pointer

int *q;  // Uninitialized (wild pointer)
q = NULL  // batter practice (assign NULL)
```

# Address of *(&)* and value of *(*)* operators 
-> *(&)* : Address of operator (veriable ka memory address deta hai). 
-> *(*)* : Defense operator, stored address ka through value of veriable deta hai. 

# Pointer Size 
Pointer ka size data type par depend nahi karta wo architecture (32bit/64bit) par depend karta hai. 

# Wild Pointer 
Jab koi pointer veriable declare to kar deta hai lekin initialize nahi karta to us time pointer random memory location point karta hai.

# Pointer Arithmetic 
Pointer arithmetic ka mtlb ya hai ki pointer ka ander stored memory address ko us data type ka size ka hisab sa increment and decrement karna possible hai aur bas itna he operation valid hai. 

# Pointer and Array 
Array ka naam he kudh ek pointer hota hai jo array ka first element ka address hold karta hai. 

## Relation between Array name and Pointer 
Array pointer nahi hai lekin array ka naam hmesa apne first element ka address represent karta hai. Isiliye array ka naam ek constant pointer ki trah behave karta hai jishka use karke hum array ka elements ko access kar shkte hai. 
## Array Vs Pointer 
Array ka size fix hota hai aur ushka base address change nahi hota qoki array ek fixed block of code hai but pointer ma base address change ho shkta hai. 

# Pointer to Pointer 
Normal pointer ek veriable ka address rakhta hai lekin pointer to pointer ek pointer ka address rakhta hai. 
## Syntax :- 
```
int x = 10; //normal veriable
int *p = &x // 'p' pointer x ka address store kar rha ha
int **PP = &p // 'pp' ek pointer ko pointer hai jo 'p' ka address rakhta hai.
```

# Pointers and Functions 
Normally jab hum functino ko veriable dete hai to wo copy pass hoti hai joki ki *call by value* kehte hai agr hume original verable modify karna ho function ka ander to ushka address pass karte hai jishko *call by reference* kehte hai. 
## Function Pointer 
Jaisa veriable ka pointer hota hai waisa he function ka v pointer hota hai. Isshe hum function ko indireclty call kar shakte hai. 
### Syntax : return_type (*pointer_name) (parameter_list); 

# Pointers and Strings 
String ek array hai to ushka naam kudh he first character ka address ko hold karta hai. 
## Treverse string through pointer 
pointer sa string traverse karna ka mtlb hai ki pointer ko string ka first character par point kara do aur phir pointer arithmetic use karke ek-ek character ko tab tak access karo jab tak '\0' (null terminator) na mil jaye. 
## String Leteral 
Jab hum direclty string ko pionter ma assign kar dete hai bina char[] array bnaye to ushe string literal kehte hai. Ya ready only hota hai ishko modify nahi kiya ja shkta hai. 

# Pointers and structures 
Structure ek user defined data type hai jo multiple veriables (different-different data types) ko ek he naam ka ander group karta hai. Jaisa hum int, float ya array ka pointer bana shkte hai waisa he hum structure ka pointer v bana shkte hai. 
## Syntax 
```
struct student *ptr;
// yaha ptr ek pointer hai jo struct student type ka address hold karta hai
```
## How to conect structure with pointers 
Man lo ek structure veriable bnaya 
struct student s1; 
Aur ek pointer bnaya 
Strucut student *ptr; 
ptr = &s1; // s1 ka address store kar diya pointer ma. 

## Access Structure members through pointer 
Normally structure members ko access karta hai
s1.roll = 101; 
s1.marks = 44.3; 

lekin pointer ka through karna ho to -> (arrow operator) ka use karan parta hai. 
ptr -> roll = 101; 
ptr -> marks = 99.3. 

## Const with pointers 
Basically ya decide karta hai ki kis cheez ko constant banaya jaye. 
1. Pointer to constant data : Mtlb data ko change nahi kar shakte par pointer ko dushre address par point kara shkte ha.
  Syntax : const int *ptr;
  - Ishka mtlb hai *ptr (data) const hai but ptr kudh const nahi hai.
  - user *ptr ka value change nahi akr shkte par ptr ko dushre veriable ka address par point kara shkte hai.

2. Constant Pointer - Mtlb pointer kudh fix hai but data change ho shakta hai.
   Syntax : int *const ptr = &a;
   - Ishka mtlb hai ptr ek he address par rhega lekin us address ka data ko modify kia ja shakta hai.
  
3. Constant pointer to constant data - Mtlb na pointer badal shkta hai aur nahi data
   Syntax : const int* const ptr = &a;


# Void Pointers 
Ya ek generic pointer hota hai jo ksi v data type ka address store kar shkta hai. 
  Syntax : void *ptr; 

# Null Pointer & Dangling Pointer 
## Null Pointer 
Ek pointer jo ksi v valid memory address ko point nahi karta ishko usually initalize karta hai NULL sa, ya use hota hai dangling pointer sa bachne ka lia aur memory allocation fail hua ya free kar diya to pointer ko NULL set karna best hai. 

## Dangling Pointer 
Jab ek local veriable banta hai to wo sirf us block/function ka lia alive rheta hai, jab function return ho jata hai to us veriable ka stack memory free/distroy ho jata hai lekin agr us veriable ka address ksi pointer ma save hai to pointer avi v alive hai aur us address ko point kar rha hai. Problem ya hai ki wo address ab valid nahi hai qoki veriable destroy ho chuka hai isi situation ma pointer ko dangling pointer kaha jata hai. 
