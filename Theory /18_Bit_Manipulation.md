# Intro 
Bit manipulation ka matlab hota hai data ke individual bits (0 aur 1) ko directly control, modify, set, clear ya toggle karna.

# Bitwise Operators 
1. *&* (Bitwise AND) - Bit 1 tabhi hoga jab dono bits 1 ho.
- Operations through AND Operator
  1) Check Bit - Check Bit ka matlab hai dekhna ki kisi number ka particular bit (kth position) set hai (1) ya unset (0). 
 
  2) Masking/Extract Specific Bits - Masking ka matlab hai ek number ke kuch specific bits ko isolate karna aur baaki bits ko ignore karna.
 
  3) Intersection of Two Bit Patters - Intersection ka matlab hai do numbers ke common set bits nikalna.

2. *|* (Bitwise OR) - Bit 1 hoga agr ksi ek me bhi 1 ho.
3. *^* (Bitwise XOR) - Different bits ho to 1.
4. *~* (Bitwise NOT) - Bit flip karta hai.
5. *<<* (Left Shift) - Bits ko left shift karta hai.
6. *>>* (Right Shift) - Bits ko right shift karta hai.

# Bit Manipulation Algorithms 
1. Bit Masking Algorithms - Bit masking algorithms wo techniques hoti hain jinme binary number ke specific bits ko set, clear, toggle ya check karne ke liye mask (special bit pattern) use kiya jata hai.
2. Bit Counting Algorithms - Bit Counting Algorithms wo algorithms hote hain jo kisi binary number me kitne bits 1 (set bits) hain ya kabhi-kabhi 0 hain, unki ginti (count) nikalte hain.
3. Bitwise Arithmetic Tricks - Bitwise arithmetic tricks wo techniques hoti hain jisme arithmetic operations (jaise multiply, divide, absolute value, power check, etc.) ko normal mathematical operators ki jagah bitwise operators (<<, >>, &, ^, etc.) se efficiently perform kiya jata hai.
4. Bitwise Searching/Testing - Bitwise searching/testing wo techniques hoti hain jisme binary number ke specific bits ko search, detect, ya test kiya jata hai — jaise kisi particular position par bit 1 hai ya 0, first set bit ka position kya hai, ya rightmost set bit kaun sa hai.
5. Bitwise Optimization Algorithms - Bitwise optimization algorithms wo techniques hoti hain jisme bit-level operations ka use karke memory usage kam kiya jata hai, performance improve ki jati hai, ya data ko compact form me store/process kiya jata hai.
6. Bitwise Cryptographic & Hashing Algorithms - Bitwise cryptographic & hashing algorithms wo algorithms hote hain jo data ko secure (encrypt) karne ya unique hash generate karne ke liye bit-level operations (jaise XOR, shifts, rotations, mixing) ka use karte hain.
