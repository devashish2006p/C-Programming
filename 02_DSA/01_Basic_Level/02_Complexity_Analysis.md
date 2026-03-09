# 1. Complexity Analysis 
Complexity Analysis ek technique hai jisse hum algorithm ke performance ko measure karte hain.
Matlab algorithm kitna fast ya efficient hai, aur kitni resources (time, memory) use karta hai.
Ye input size ke hisaab se algorithm ka behavior analyze karta hai.

# 2. Types of Complexity
- 1. Time Complexity - Ya btata hai algorithm ko complete hone ma kitna time lgega. 
  - Types of Time Complexity :-
        - 1. Best Case - Best Case ek aisa scenario hai jahan algorithm ko minimum possible time me execute karna padta hai, yani input aise hota hai jo algorithm ke liye ideal hai. Ya sbse fast execution scenario ko represent karta hai. Har step ka lia minimum iteration ya comparison lagti hai.
        - 2. Worst Case - Worst Case ek aisa scenario hai jahan algorithm ko maximum possible time lagta hai, yani input aisa ho jo algorithm ke liye sabse inefficient ho. Ya sbse slow execution scenario ko represent karta hia. Har step ka lia maximum iteration ya comparision karni parti hai.
        - 3. Average Case - Average Case ek scenario hai jahan algorithm ka execution time expected ya typical input ke liye calculate kiya jaata hai, yani input randomly distributed hai. Ya practical scenario ka realistic estimate deta hai naki ideal (best) ya extreme (worst) case. Calculation ma hum har possible input ka probability consider karte hai aur average nikalte hai.

- 2. Space Complexity - Ya btata hai algorithm ko complete karne ma kitna memory space lgega. 
  - Types of Space Complexity :-
        - 1. Fixed Part : Fixed part space complexity ka wo hissa hota hai jo input size par depend nahi karta aur program execute hone ka dauran constant memory use karta hai. Ishme usually simple variables, constants, program instructions aur fixed size data structures aate hai.
        - 2. Variable Part : Variable part space complexity ka wo hissa hota hai jo input size ka sath change hota hai yani jitna bada input hoga utni zyada memory lgegi. Ishme usually arrays, dynamic memory allocation, recursion stack aur input data storage aata hai.

# 3. Notations
- 1. Big O : Ya algorithm ka maximum growth rate ko represent karta hai, yani worst case scenario ma algorithm kitna time ya space le shkta hai. 

- 2. Big Omega : Ya algorithm ka minimum growth rate ko represent karta hai, yani best case scenario ma algorithm sbse kam kitna time ya space lega. 

- 3. Big Theta : Ya algorithm ka exact growth rate ko represent karta hai jab upper bound aur lower bound dono same ho.

# 4. Complexity Growth Orders 
Complexity growth order btata hai ki input size badhne par algorithm ka time ya memory kitna speed sa increase hota ha. 
1. O(1) → Constant : Jab algorithm ka execution time input size (n) se bilkul change nahi hota, use constant complexity kehte hain.

2. O(log n) → Logarithmic : Jab algorithm har step me problem size ko divide karta hai, to uski complexity logarithmic hoti hai.

3. O(n) → Linear : Jab algorithm ka time input size ke direct proportional badhta hai.

4. O(n log n) → Linearithmic : Jab algorithm me linear processing aur logarithmic division dono combine hote hain.

5. O(n²) → Quadratic : Jab algorithm me nested loops ho jahan ek loop dusre ke andar n times chale.

6. O(2ⁿ) → Exponential : Jab algorithm ka steps 2^n rate se increase karte hain, use exponential complexity kehte hain.

7. O(n!) → Factorial : Jab algorithm n! permutations explore karta hai, use factorial complexity kehte hain.

# 5. Amortized Analysis
Amortized Analysis ek technique hai jisme operations ki average cost ko analyze kiya jaata hai jab operations ko ek sequence me perform kiya jaata hai, taki overall cost per operation samajh aaye.
