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
