# 1. System Software
System software wo software hai jo computer hardware aur application software ke beech bridge ka kaam karta hai. Ye hardware ko control karta hai aur application software ko execute karne ke liye environment provide karta hai.

---

# 2. Types of System Software
## 2.1 Operating System (OS) 
OS ek master control program hai jo computer hardware aur software resources ko manage karta hai. 

## 2.2 Utility Software
Utility software special-purpose programs hai jo computer system ki efficiency aur maintenance improve karte hain.

## 2.3 Device Drivers 
Device driver ek special program hai jo operating system aur hardware device ka beech communication ka kaam karta hai. 

## 2.4 Language Translators 
Ye software high-level language programs ko machine language me convert karte hain taaki CPU execute kar sake.

---

# 3. User Space vs Kernel Space 
## 3.1 Kernel Space 
Kernel space wo memory area hai jahan OS kernel aur device drivers run karte hain aur jo protected hota hai, jise user programs directly access nahi kar sakte.

## 3.2 User Space 
User space wo memory area hai jahan user applications aur processes run karte hain aur jo limited access ka hota hai, jisse hardware directly access nahi kiya ja sakta.

---

# 4. System Architecture Overview
## 4.1 Definition 
System Architecture ek aisa blueprint ya design hai jo batata hai ki computer ka hardware aur software components kaise interact karte hain aur kaunse resources kaise manage hote hain.

## 4.2 Main Components of System Architecture 
1. Input Devices - Ya devices data aur instructions ko system main feed karta hai.
2. Output Devices - Ya devices processed data ko user ko dikhate hai.
3. CPU - It is a brain of computer sab calculation aur decision yahi hoti hai.
   - Components of CPU :-
     1. ALU (Arithmetic Logic Unit) - Ya calculations aur logical operations karta hai.
     2. Control Unti (CU) - Instruction fetch, decode aur execution ko control karta hai.
     3. Registers - Temporary storage for high speed processing.
4. Memory/Storage - Ishme data temporary/permanently store kia jate hai.
5. System Bus - Communication path jo CPU, memory aur I/O devices ko connect karta hai.
6. Software/System Software - OS aur system utilities hardware ko control aur manage karte hai. 

# 5. Bit Manipulation
## 5.1 Bitwise Operators 
1. AND (&) - Ya do bits ko compare karke tabhi 1 return karta hai jab dono bits 1 ho warna 0 deta hai.
2. OR (|) - Ya do bits ma se ksi bhi ek bit ke 1 hone par 1 return karta hai, warna 0 deta hai.
3. XOR (^) - Ya tab 1 return karta hai jab dono bits alag ho (ek 0 aur ek 1) aur same hone par 0 hota hai.
4. NOT (~) - Ya har bit ko invert karta hai, yani 1 ko 0 aur 0 ko 1 bana deta hai.
5. Left Shift (<<) - Ya bits ko left shift karta hai jisshe number ka value multiply hota hai, generally 2 sa.
6. Right Shift (>>) - Ya bits ko right side shift karta hai jisshe number ka value divide hota hai generally 2 sa.

## 5.2 Bit Manipulation Operations
1. Set bit - Set bit operation kisi specific position par present bit ko 1 bana deta hai, chahe woh pehle 0 ho ya 1. Ishko krne ka lia ksi K-th position ki bit ko 1 banane ka lia hum OR operation use karte hai. 
- Formula : x = x | (1 << k);
2. Clear bit

3. Toggle bit

4. Check bit

5. Get bit

6. Left shift

7. Right shift

8. Even/Odd check

9. Power of 2 check

10. Remove Rightmost Set bit

11. Get rightmost set bit

12. Count set bits

13. Clear all bits

14. Set all bits

15. Toggle all bits
