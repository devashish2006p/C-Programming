# 1. Basic Intro
Array ek data structure hai jisme same data type ke multiple values ko ek hi variable name ke under store kiya jata hai.

# 2. Memory Allocation Methods of an Array
## 1. Static Arrays 
Static array wo array hota hai jiska size program compile hone se pehle hi fix ho jata hai aur runtime par change nahi kiya ja sakta.
- Example
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
