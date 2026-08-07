# 1. Stack 
Stack ek linear data structure hai jisme data ka insertion (Push) aur deletion (Pop) sirf ek hi end, yani Top, se hota hai aur ye LIFO (Last In, First Out) principle ko follow karta hai.

# 2. LIFO Principle 
LIFO (Last In, First Out) ek principle hai jisme Stack me jo data element sabse last me insert (push) hota hai, wahi element sabse pehle remove (pop) hota hai, kyunki insertion aur deletion dono sirf Stack ke ek hi end (Top) se perform hote hain.

# 3. Terminologies
1. Top - Top Stack ka wo end (position) hota hai jahan se Stack me saare insertion (Push) aur deletion (Pop) operations perform kiye jaate hain. Stack me hamesha sirf Top element ko access kiya ja sakta hai, kyunki Stack LIFO principle follow karta hai aur beech ke elements ko directly access nahi kiya ja sakta.
2. Bottom - Bottom Stack ka wo end hota hai jahan Stack ka sabse pehla element store hota hai, yani jo element sabse pehle insert hua tha. Bottom Stack ka fixed base hota hai aur Stack ke normal operations (Push aur Pop) directly Bottom se perform nahi hote hain.
3. Push - Push Stack me naye element ko Top position par insert karne ki process hoti hai, jisme Stack ka Top update hokar naye inserted element ko point karta hai.
4. Pop - Pop Stack ke Top element ko remove karne ki process hoti hai, jisme Top wala element delete hota hai aur uske neeche wala element naya Top ban jata hai.
5. Peek/Top - Peek operation Stack ke Top element ki value ko bina remove kiye dekhne ke liye use hota hai, yani ye sirf Top element return karta hai aur Stack me koi change nahi karta.
6. Overflow - Stack Overflow tab hota hai jab Stack apni maximum storage capacity tak bhar chuka hota hai aur hum usme ek aur naya element insert (Push) karne ki koshish karte hain.
7. Underflow - Stack Underflow tab hota hai jab Stack empty hota hai aur hum usme se element remove (Pop) karne ki koshish karte hain.

# 4. Stack Operations
1. Push - Push operation ka use Stack ke Top par ek naya element insert karne ke liye hota hai, jisme naya element add hone ke baad wahi element Stack ka naya Top ban jata hai.
2. Pop - Pop operation ka use Stack ke Top element ko remove karne ke liye hota hai, jisme Top element delete hota hai aur uske neeche wala element naya Top ban jata hai.
3. Peek - Peek operation ka use Stack ke current Top element ki value ko dekhne ke liye hota hai bina us element ko remove kiye.
4. isEmpty - isEmpty operation check karta hai ki Stack ke andar koi element present hai ya nahi; agar Stack me koi element nahi hota hai to ye true return karta hai.
5. isFull - isFull operation check karta hai ki Stack apni maximum capacity tak bhar chuka hai ya nahi; agar Stack full hai to ye true return karta hai.
