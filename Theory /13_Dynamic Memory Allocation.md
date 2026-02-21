# Static Memory Allocation 
Static Memory Allocation ka matlab hai ki program ke variables ke liye memory compile time pe reserve ho jaati hai. Matlab program chalne se pehle hi memory fix ho jaati hai aur poore execution ke dauraan same rehti hai. Ye mostly use hoti hai global variables, local variables, aur fixed-size arrays ke liye jaha memory requirement pehle se pata hoti hai.

## Advantages of Static Memory Allocation
  1. Efficiency: Memory ek hi baar allocate hoti hai compile time pe, isliye runtime pe overhead nahi hota aur program fast execute hota hai.
  
  2. Simplicity: Programmer ko manually allocate/free karna nahi padta.
  
  3. Predictability: Memory usage pehle se known hoti hai, isliye program ka behavior consistent hota hai.
  
  4. No Fragmentation: Dynamic allocation ki tarah fragmentation ka issue nahi hota.

## Disadvantages of Static Memory Allocation
1. Fixed Size: Memory size compile time pe decide karna padta hai, runtime pe change nahi hota.

2. Rigidness: Dynamic allocation ki flexibility nahi hoti.

3. Memory Waste: Agar zyada allocate kar diya to waste, kam allocate kiya to crash/error.

4. Known Size Only: Sirf wahi cases jaha memory size pehle se pata ho, runtime dependent cases ke liye suitable nahi hai.

# Dynamic Memory Allocation (DMA) 
DMA ka matlab hota hai program ka chalne ka time par memory ko allocate karna aur free karna, intstead of compile time fixed size. C ma ya kaam <stdlib.h> library ka functions karte hai. 

# Functions of DMA 
1. malloc() : Memory allocate karta hai but values uninitialized hoti hai.
   - Syntax : int *arr = (int*) malloc(size of arr * sizeof(int));
2. calloc() : Memory allocate karta hai aur sabhi values ko 0 sa initialize v karta hai
   - Syntax : int *arr = (int*) calloc(size of arr, sizeof(int));
3. realloc() : pehla sa allocated memory ko resize karta hai
   - Syntax : arr = (int*) realloc(arr, 10 * sizeof(int));
4. free() : dynamically allocated memory ko wapas systam ko de deta hai.
   - Syntax : free(arr);
              arr = NULL;

# Best Practices for Dynamic Memory Management

1. Memory allocate karne ke baad hamesha NULL check karo.  

2. Allocation ke liye hamesha sizeof(type) ka use karo, hard-coded size avoid karo.  

3. Har malloc ka exact ek free hona chahiye.  

4. Free karne ke baad pointer ko NULL set kar dena chahiye.  

5. Array ki boundary kabhi cross nahi karni chahiye.  

6. Memory ko free karne ke baad usko access nahi karna chahiye.  

7. Double free se hamesha bachna chahiye.  

8. realloc use karte waqt original pointer ko directly overwrite nahi karna chahiye.  

9. Memory leak se bachne ke liye proper cleanup strategy follow karni chahiye.  

10. Large programs me memory debugging tools ka use karna chahiye.  
 
