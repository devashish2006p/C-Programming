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
Insertion ka matlab hai array me kisi new element ko kisi specific position par add karna.
#include <stdio.h>
- Example :-
    ```
    int main() {
        int arr[6] = {10,20,30,40,50};
        int pos = 2;
        int value = 25;
    
        for(int i = 5; i > pos; i--) {
            arr[i] = arr[i-1];
        }
    
        arr[pos] = value;
    
        for(int i = 0; i < 6; i++) {
            printf("%d ", arr[i]);
        }
    }
    ```
- *Note : Array ma insertion tabhi possible hota hai jab array ma kam sa kam ek khali jagha ho, warna new element add nhi kiya ja shkta hai. Full array ma insertion nhi hoga jab tak size increase na kiya jaye.*

# 5. Deletion 
Deletion ka matlab hai array me kisi specific position ke element ko remove (delete) karna aur uske baad wale elements ko left shift kar dena.
- Example :-
  ```
  #include <stdio.h>

    int main() {
    
        int arr[5] = {10,20,30,40,50};
        int pos = 2;   // jis index ka element delete karna hai
    
        // Left shift karenge
        for(int i = pos; i < 4; i++) {
            arr[i] = arr[i+1];
        }
    
        // Array print
        for(int i = 0; i < 4; i++) {
            printf("%d ", arr[i]);
        }
    }
  ```
- *Note : Array ma deletion ka main kaam overwrite hi hota hai, yani next elements ko left shift karke previous position par copy (overwrite) kar diya jata hai. Deletion in Arry = Left shift + overwrite.*
