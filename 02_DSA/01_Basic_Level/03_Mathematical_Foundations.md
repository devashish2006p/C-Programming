# 1.  Logarithm
Logarithm ek mathematical operation hai jo batata hai ki kisi base ko kitni power par raise karne par given number milta hai.
- *DSA ma logarithm algorithm ki speed measure karne ma use hota hai.*
- Example :-
- log*b*(a) = c (Mtlb *b* ko kis power c par raisa karne par a milega?);
- log*2*(32) = 5.
## 1.1 Components of Logarithm
1. Base (b) - Ya wo number hota hai jishko power par raisa kiya jata hai. 
2. Argument/Number (a) - Ya wo value hota hai jiska logarithm nikalna hota ha. 
3. Result/Log value (c) - Ya wo power hota hai jo base par lagti hai taki given number mile.

## 1.2 Types of Logarithm
1. Common Logarithm - Common logarithm wo logarithm hai jiska base 10 hota hai, aur yeh batata hai ki 10 ko kis power par raise karne par given number milta hai.
  Ex - log*10*(100) = 2. 
2. Natural Logarithm - Natural logarithm wo logarithm hai jiska base e = ~2.718 hota hai aur yeh btata hai ki e ko kis power par raise karne par given number milta hai. 
3. Binary Logarithm - Binary logarithm wo logarithm hai jiska base 2 hota hai, aur yeh batata hai ki 2 ko kis power par raise karne par given number milta hai.

# 2. Exponent Rules 
Exponent Rules ka mtlb hai power ka mathematical rules jo btata hai ki jab ksi number ko power diya jata hai to ushke sath calculations kaisa karni hai. 
1. Product Rule : Agr same base wale powers multiply ho rhe ho to unke exponents add ho jate hai.

2. Quotient Rule : Agr same base wale powers divide ho rhe ho to exponents subtract ho jate hai.

3. Power of a Power Rule : Agr ksi power ko fir sa power diya jaye to exponents multiply ho jate hai.

4. Power of a Product Rule : Agr product (multiplication) ko pwer diya jaye to har factor ko alag-alag power mil jati hai.

5. Power of a quotient Rule : Agr fraction ko power diya jaye to numerator aur denominator dono ko power mil jata hai.

6. Zero Exponent Rule : Koi bhi non-zero number agar power 0 par ho to result 1 hota hai.

7. Negative Exponent Rule : Negative exponent ka mtlb hota hai reciprocal (Ulta fraction). Mtlb agr exponent negatve ho jaye to base denominator ma chala jata hai. 

8. Fractional Exponent Rule : Fractional exponent ka mtlb root hota hai.

# 3. Summations 
Summations ka mtlb hota hai bahut sare numbers ya expressions ko ek systematic tareeke sa add(sum) karna. Ya ek mathematical method hai jishme ks isequence ka multiple terms ko ek sath add kiya jata hai. Ishko Greek Letter Sigma (∑)sa represent kiya jata hai. 
Computer Science ma summation ka mtlb hai loops aur algorithms ka total operations ko mathematically calculate karna. 

## 3.1 Summation Notation 
Summation notation ek mathematical shorthand hai jisshe bahut sare numbers ko add karne ko short form ma likha jata hai. 
- Parts of Summation Notatoin :-
  ```
  Σ i
  i = 1 to 5
  ```
  1. ∑ (Sigma) = Mtlb -> add kro
  2. i = 1 = Mtlb counting 1 sa start hogi
  3. 5 = Mtlb 5 tak chalegi
  4. i = Jo number add ho rha hai.
      
## 3.2 Basic Summation Formulas
1. Constant Sum : Ishka mtlb hai ki agr ksi loop ya algorithm ma har iteration ma same amount ka work ho to total work iterations ki count ka proportional hota hai. Mtlb agr loop n baar chalta hai aur har bar same kaam karta hai to total kaam n times hoga. 
- Example :-
  ```
  for(int i = 1; i <=n; i++){
  printf("Hello"); 
  }
  ```
  - Explanation :- 
    - loop n times run krega
    - har iteration ma same kaam ho rha hai (print)
    - To total operation n hua.
  
- Ishka use mainly single loops analyze karne ma
- Simple algorithms ki time complexity nikalne ma
- Iteration based algorithms ma hota hai. 

2. Sum of ones : Ishka mtlb hai ki agr algorithm ya loop ma har iteration ek simple operation kare, jishka cost 1 mana jata hai, to total iterations ka count ka equal hota hai. Mtlb agr loop n baar chalta hai aur har bar ek unit operation karta hai to total operations n hote hai.

- Example :-
  ```
  for(int i = 1; i <= n; i++)
  {
    x++;

  }
  ```
  - Explanation:
    - loop n times run karega
    - har iteration me 1 operation ho raha hai
   
3. Sum of Natural Numbers : Ishka mtlb hai jab ksi algorithm ya loop ma work har iteration ma gradually badhta hai (1, 2, 3, 4......pattern ma). Mtlb first iteration 1 operation, second iteration 2 operations, third iteration 3 operations.
   - Example :-
   ```
   for(int i = 1; i <= n; i++)
   {
      for(int j = 1; j <= i; j++)
      {
          printf("Hi");
      }
    }
    ```
4. Sum of squares - Sum of Squares ka matlab hai ki kisi algorithm ya nested loops me work har iteration me i² ke pattern me badh raha ho.

5. Sum of Cubes - Sum of Cubes ka matlab hai ki kisi algorithm ya nested loops me work har iteration me i³ ke pattern me badh raha ho.

6. Arithmetic series - Arithmetic Series ka matlab hai algorithm ya loop me work har iteration me ek fixed amount se increase ya decrease hota ho.

7. Geometric series - Geometric Series ka matlab hai algorithm ya loop me work har iteration me ek fixed ratio se multiply ho raha ho.

8. geomatric series (infinite case) - Infinite geometric series tab hoti hai jab algorithm me work har iteration me ek fixed ratio se multiply ho raha ho aur iterations infinite tak continue ho sakti ho, lekin ratio 0 < r < 1 ho jisse total work finite rahe.

9. Logarithmic sum - Logarithmic Sum ka matlab hai algorithm me work har iteration me log(i) ke pattern me badh raha ho.

10. Harmonic Series - Harmonic Series ka matlab hai ki algorithm me work har iteration me 1/i ke pattern me kam hota hai.

11. Power of Two sum - Power of Two Sum ka matlab hai ki algorithm me work har iteration me 2 ke powers ke pattern me badh raha ho.

12. Linear Combinatoin Rule - Linear Combination Rule ka matlab hai ki agar hum ek ya ek se zyada summations ko ek saath multiply ya add karke likhte hain, to hum unko algebraically separate ya combine kar sakte hain.

13. polynomial bound - Polynomial Bound ka matlab hai ki kisi algorithm ka work ya summation function n ke power ke form me bounded ho.

14. Harmonic with constant - Harmonic with Constant ka matlab hai ki algorithm me har iteration ka work constant + 1/i ke pattern me ho, jisse total work ~ O(n) (linear) hota hai, aur logarithmic part small contribution deta hai.

## 3.3 Loop ko summation ma convert karna 

## 3.4 Summation simplify karna 

## 3.5 Time complexity derive karna 

# 4. Recurrance relations
# 5. Recursion Trees
# 6. Master Theorem
# 7. Probability Basics 
# 8. Combinatorics basics 
# 9. Moduler Arithmetic 

​
