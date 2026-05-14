# 1. Basic Intro
Array ek data structure hai jisme same data type ke multiple values ko ek hi variable name ke under store kiya jata hai.

# 2. Memory Allocation Methods of an Array
## 1. Static Arrays 
Static array wo array hota hai jiska size program compile hone se pehle hi fix ho jata hai aur runtime par change nahi kiya ja sakta.
- Example:-
  ```
    - int arr[5] = {10, 20, 30, 40, 50};
  ```  
## 2. Dynamic Arrays
Dynamic array wo array hota hai jiska size program run hone ke time (runtime) par decide hota hai aur zarurat padne par change bhi kiya ja sakta hai.
- Example :- 
    ```
    - #include <stdio.h>
      #include <stdlib.h>
      int main() {
          int n;
          printf("Enter size: ");
          scanf("%d", &n);
          int *arr = (int*) malloc(n * sizeof(int));
      }
     ```
# 3. Traversal 
Traversal ka matlab hai array ke sabhi elements ko ek-ek karke access ya visit karna (usually loop ki help se).
- Example :-
  ```
    #include <stdio.h>

    int main() {
        int arr[5] = {10,20,30,40,50};

    for(int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    }
  ```

# 4. Insertion 
## 4.1 About
Insertion ka matlab hai array me kisi new element ko kisi specific position par add karna. Ishka objective existing data structure ma naya lement add karna hota hai while maintain the strucutre/order. 

## 4.2 Working Mechanism 
1. Insert karne ka lia target position choose ki jati hai.
2. Check kiya jata hai ki array me free space hai ya nahi.
3. Target position ka baad wale elements ko right shift kiya jata hai.
4. New element ko target position par store kiya jata hai.
5. Array ka logical size increase ho jata hai.

## 4.3 Internal Decision Logic
1. System decide karta hai insertion kis position par hoga.
2. Check hota hai ki valid index hai ya nahi.
3. Check hota hai ki array full to nahi hai.
4. Decide hota hai kitne elements shift karne parenge.
5. Elements ko last se reverse order ma shift kiya jata hai taki data overwrite na ho.
6. Empty bani position ma new element insert kar diya jata hai.

## 4.4 Time Complexity Analysis
- Best Case : O(1)
- Average Case : O(n)
- Worst Case : O(n)

## 4.5 Space Complexity Analysis
- Fixed Array : O(1)
- Input dependent/dynamic sized array : O(n) 

- *Note : Array ma insertion tabhi possible hota hai jab array ma kam sa kam ek khali jagha ho, warna new element add nhi kiya ja shkta hai. Full array ma insertion nhi hoga jab tak size increase na kiya jaye.*

# 5. Deletion 
Ishka mtlb hota hai array ma se ksi specific position ka element remove karna aur baki elements ko shift karke array ka order maintain rakhna. 
- **Working Mechanism**
  - 1. User delete karne ka lia ek position specify karta hai.
    2. Us position ka element identify kiya jata hai.
    3. Us element ko logically remove kiya jata hai (overwrite/skip). 
    4. Ushke baad ka sare elements ko left side shift kiya jata hai.
    5. Last position ko empty ya invalid mark kiya jata hai.
    6. Array ka logical size 1 reduce ho jata hai.
- **Internal Decision Logic**
  - 1. System check karta hai ki given index valid hai ya nahi.
    2. Check hota hai ki array empty to nahi hai.
    3. Decide hota hai ki kaunsa element delete karna hai.
    4. Shift operation calculate hota hai (kitne elements left move honge).
    5. Elements ko left shift karke gap fill kiya jata hai.
    6. Last index ko update karke size decrement kar diya jata hai. 
- *Note : Array ma deletion ka main kaam overwrite hi hota hai, yani next elements ko left shift karke previous position par copy (overwrite) kar diya jata hai. Deletion in Arry = Left shift + overwrite.*

# 6. Searching in Array 
Array me searching ka matlab hota hai kisi specific element (value) ko find karna — ki wo array me exist karta hai ya nahi, aur agar karta hai to kis position (index) par hai.

## 6.1 Core Types of Searching in Array 
1. Linear Search - Linear search ek simple searching technique hai jisme hum array ke har element ko starting se end tak ek-ek karke check karte hain, jab tak required element mil na jaye ya pura array khatam na ho jaye.

2. Binary Search - Binary search ek efficient searching technique hai jisme hum sorted array ko use karke element ko find karte hain by repeatedly array ko half (aadha-aadha) me divide karte hue.
