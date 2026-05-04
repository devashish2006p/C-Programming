# 1. Intro 
Bit manipulation ka matlab hota hai data ke individual bits (0 aur 1) ko directly control, modify, set, clear ya toggle karna.

# 2. Bitwise Operators 
1. AND (&) - Ya do bits ko compare karke tabhi 1 return karta hai jab dono bits 1 ho warna 0 deta hai.
2. OR (|) - Ya do bits ma se ksi bhi ek bit ke 1 hone par 1 return karta hai, warna 0 deta hai.
3. XOR (^) - Ya tab 1 return karta hai jab dono bits alag ho (ek 0 aur ek 1) aur same hone par 0 hota hai.
4. NOT (~) - Ya har bit ko invert karta hai, yani 1 ko 0 aur 0 ko 1 bana deta hai.
5. Left Shift (<<) - Ya bits ko left shift karta hai jisshe number ka value multiply hota hai, generally 2 sa.
6. Right Shift (>>) - Ya bits ko right side shift karta hai jisshe number ka value divide hota hai generally 2 sa.

# 3. Bit Manipulation Operations
1. Set bit - Set bit operation kisi specific position par present bit ko 1 bana deta hai, chahe woh pehle 0 ho ya 1. Ishko krne ka lia ksi K-th position ki bit ko 1 banane ka lia hum OR operation use karte hai. 
- Formula : x = x | (1 << k);
  
2. Clear bit - Ya ek operation hai jisme ksi binary number ka ander ek specific position ki bit ko 0 me badal diya jata hai, chahe wo pehle 1 ho ya 0, aur baki sab bits ko unchanged rakha jata hai. 
- Formula : x = x & ~(1 << k);
  
3. Toggle bit - Ya ek operation hai jisme ksi specific position ki bit ko ushke opposite me badal diya jata hai, yani 0 ko 1 aur 1 ko 0. 
- Formula : x = x ^ (1 << k);
  
4. Check bit - Ya ek operation hai jisme ksi binary number ka ander ek specific position ki bit 1 hai ya 0, ya pata lagaya jata hai bina original value ko change kiye. 
- Formula : x & (1 << k)
  
5. Get bit - Ya ek operation hai jisme ksi binary number ka ander ek specific position ki bit ka exact value nikal kar return kiya jata hai, bina original number ko change kiye. 
- Formula : bit = (x >> k) & 1
  
