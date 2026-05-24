# 1. Recursion
Ya ek aisi technique hai jisme koi fucntion ksi problem ko solve karne ka lia khud ko bar-bar call karta hai, jab tak stopping condition na mil jaye. 

--- 

# 2. Recursive Thinking 
Ishka mtlb hota hai ksi bade problem ko usi type ka chote version ma todkar sochna aur maana ki chota version already solve ho jayega. 

---

# 3. Components of Recursion
1. **Base Case** - Ya recursion ka woh part hota hai jahan function khud ko call karna band kar deta hai aur directly result return karta hai.
2. **Recursive Call** - Ya wo process hota hai jisme function apne hi ander khud ko dobara call karta hai taki same type ka smaller problem ko solve kar sake.
3. Smaller Problem - Har recursive call ma problem pehle sa chota ya simpler hona cahiya taki eventually base case tak paucha ja sake.

---

# 4. Types of Recursion
## 4.1 Direct Recursion - Ya ek aisa recursion type hota hai jisme koi function apne hi function body ka ander direclty khud ko call karta hai problem ko smaller parts ma solve karne ka liye aur ye process base case milne tak repeat hota rehta hai. 


## 4.2 Indirect Recursion

## 4.3 Tail Recursion 
Ya ek aisa recursion type hota hai jisme function current processing ya current situation ko pehle execute karta hai aur recursive call ko function ka last operation ka roop ma perform karta hai, jiske baad function me koi kaam pending nahi bachta. 

## 4.4 Head Recursion 
Ya ek aisa recursion type hota hai jisme function pehle recursive call perform karta hai aur current processing ya current situation ko recursive calls complete hone ka baad execute karta hai. 

## 4.5 Linear Recursion 
Ya ek aisa recursion type hota hai jisme har function call apne execution ka dauran sirf ek hi recursive call generate karta hai, jiski wajah sa recursion ek single straight line chain ki tarah progress karta hai from one call to the next until base case is reached. 

## 4.6 Tree Recursion 

## 4.7 Nested Recursion

## 4.8 Binary Recursion

## 4.9 Multple Recursion 

## 4.10 Mutual Recursion 

---

# 5. Internal Mechanism 
1. Jab recursive function call hota hai tab system function ka lia memory me ek naya stack frame create karta hai.
2. Us stack frame ma functions ka :-
   - Parameters
   - Local variables
   - return address
   - current execution state store kiya jate hai.
3. Naya stack frame program ka call stack ka top par push ho jata hai.
4. Function execute hona start karta hai aur check karta hai ki base case mila ya nahi.
5. Agr base case nahi milta to function smaller problem ka sath khud ko dobara call karta hai.
6. Har naye recursive call par system fir sa ek naya stack frame create karta hai aur unko stack ka top par push kar deta hai.
7. Ya process continuously repeat hota rehta hai jab tak base case na mil jaye.
8. Jab base case mil jata hai, function further recursive call karna band kar deta hai aur value return karna start karta hai.
9. Return hote waqt current stack frame stack sa remove (pop) ho jata hai.
10. Control previous recursive call par wapas chala jata hai.
11. Fir previous fucntion apna remaining kaam complete karta hai aur return karta hai.
12. Ya reverse returning process tak tak chalta hai jab tak sabhi stack frames remove na ho jayein aur control original caller tak wapas na aa jaye

---

# 6. Recursion Vs Iteration 
- **Iteration** : Iteration ka mtlb hota hai loops ka through repeated execution. Ishme same function ka ander loop repeatedly chalta hai aur condition false hone par ruk jata hai. Ishme same memory block reuse hota hai. Iteration comparitavely recursion sa faster hoti hai qoki ishme same memory overwrite ho rha hota hai. 
- **Recusion** : Recursion ma function khud ko repeatedly call karta hai ishme har call ka naya stack frame banata hai, function calls stack ma store hote hai aur base case par returning start hoti hai. Ishme har call ek naya frame banata hai. Recursion comparitavely iteration sa slower hoti hai qoki ya new stack frames create karta hai naki overwrite. 
   
