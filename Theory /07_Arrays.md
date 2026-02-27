# Array 
Ek array C language mein ek linear data structure hota hai jo ek hi data type ke multiple values ko ek saath store karta hai. Ye values contiguous memory locations mein rakhe jaate hain, aur har element ko ek unique index ke through access kiya ja sakta hai. Indexing hamesha 0 se start hoti hai.

# Declaration and Initialization of Arrays 

## Declaration of Arrays
C mein arrays ko use karne se pehle declare karna zaroori hota hai.  
Declaration mein data type aur size specify karna padta hai.  
Isse memory allocate hoti hai aur undefined values avoid hoti hain.  

**Syntax**:  
Data type ke baad array ka naam aur square brackets mein size likha jaata hai.  
int arr[size]; 
---

## Initialization of Arrays
Arrays ko declare karte hi initialize kiya ja sakta hai ya baad mein alag-alag elements ko assign kiya ja sakta hai.  

### Initialization Methods
- **At Declaration**: Curly braces `{}` use karke values assign karte hain. Agar kuch elements initialize nahi kiye gaye to wo default zero ho jaate hain.  
- **Without Declaring Size**: Agar values pata hain par size nahi, to C automatically size determine kar leta hai based on number of elements.  
- **Individual Assignment**: Declaration ke baad har element ko alag-alag index ke through assign kiya ja sakta hai.  

---

## Best Practices for Arrays
- **Meaningful Names**: Array ka naam us data ko represent kare jo store ho raha hai (jaise scores, temperatures).  
- **Proper Size**: Size itna rakho ki overflow na ho aur memory waste bhi na ho.  
- **Initialization**: Arrays ko declare karte hi initialize karo ya default value set karo taaki undefined behaviour avoid ho.  
- **Bounds Check**: Array ke declared size se bada index access mat karo, warna

# Types of Arrays in C 

## One-Dimensional Arrays
One-dimensional array ek data structure hai jo ek hi type ke elements ko ek straight line mein store karta hai.  
Har element ek unique index ke through access hota hai, aur indexing hamesha 0 se start hoti hai.  
Array ka size batata hai ki kitne elements store kiye ja sakte hain.  

### Declaration Syntax for a One-Dimensional Array is
    data_type array_name[array_size];

    data_type: It is the type of data the array holds, such as an int, float, char.
    array_name: The name is assigned to the array in order to let it access its elements.
    array_size: It indicates the number of elements the array will hold.

- Access aur modification index ke zariye hota hai. Matlab tum kisi element ko read ya overwrite kar sakte ho uske index ke basis par. Ek common operation hota hai array ke saare elements ko loop ke through process karna, jaise sum calculate karna.  

## Two-Dimensional Arrays
Two-dimensional array ko matrix bhi kehte hain. Ye ek grid hota hai jo rows aur columns mein organize hota hai.  
Har element ko access karne ke liye do indices use hote hain: ek row ke liye aur ek column ke liye.  
Declaration mein rows aur columns specify kiye jaate hain. Agar initialization complete na ho to baaki elements default zero set ho jaate hain.  
Nested loops use karke 2D array ke elements traverse kiye jaate hain, outer loop rows ke liye aur inner loop columns ke liye.  

### Declaring and Initializing Two-Dimensional Arrays
A two-dimensional array in C is declared using the square brackets []. It is describedas the number of rows and columns. 
  Syntax:
  data_type array_name[rows][columns];
    data_type: It declares the data type of data stored in the array. For example, int, float, char. 
    array_name: This is the name assigned to the array.
    Rows and Columns: The dimensions of the array, specifying the number of rows andcolumns

## Multi-Dimensional Arrays
Multi-dimensional arrays one aur two-dimensional arrays ka extension hote hain. Ye higher dimensions mein data store karte hain, jaise 3D arrays.  
Har dimension ke liye ek index hota hai, aur nested loops use karke har dimension traverse kiya jaata hai.  
3D arrays ko ek stack of 2D matrices ke form mein socha ja sakta hai. Har layer ek 2D matrix hoti hai aur multiple layers milke 3D structure banate hain.  
Har dimension ke liye alag loop hota hai jo elements ko systematically access karta hai.  
### Declaration Syntax of 3D Array :
  data_type array_name[size1][size2][size3];
    data_type : What kind of data the array contains, for example, int, float or char. 
    array_name: Name of the array
    size1, size2, size3 : Dimensions sizes, for example rows, columns and depth.

# Operations on Array 

  1. Traversal – Har element ko sequentially access karna.
  
  2. Insertion – Kisi index par naya value dalna.
  
  3. Deletion – Kisi element ko remove ya overwrite karna.
  
  4. Searching – Kisi specific element ko find karna.
  
  5. Sorting – Elements ko ascending/descending order mein arrange karna.
  
  6. Merging – Do arrays ko combine karna.
  
  7. Splitting – Ek array ko multiple arrays mein todna.
  
  8. Updating/Modification – Kisi element ki value change karna.
  
  9. Copying – Ek array ke elements ko dusre array mein copy karna.
  
  10. Reversing – Array ke elements ko ulta karna (last se first).

# Indexing in Arrays
Indexing ka mtlb hai array ka elements ko access karna using their position (index). Array ka elements continuous memory blocks ma store hote hai. Har element ka ek unique index number hota hai jo 0 sa start hota hai. Index ke through tum directly ksi bhi element ko access, modify ya traverse kar shkte ho. 
## Ways of Indexing in arrays
1. Direct Indexing - Direct indexing ek simple method hai jisme array ke element ko uske index number ke through directly access kiya jaata hai.
- Example :-
  ```
  #include <stdio.h>
    int main() {
        int arr[5] = {10, 20, 30, 40, 50};
        printf("%d\n", arr[0]); // Output: 10 (first element)
        printf("%d\n", arr[3]); // Output: 40 (fourth element)
        return 0;
    }
    ```
2. Sequential Indexing - Sequential indexing ka matlab hai array ke elements ko ek sequence me (order-wise) access karna, usually loop ke through, jisme har index ko ek-ek karke traverse kiya jaata hai.
   - Example :-
     ```
     #include <stdio.h>
        int main() {
            int arr[5] = {10, 20, 30, 40, 50};
            for(int i=0; i<5; i++) {
                printf("%d ", arr[i]);  
            }
            // Output: 10 20 30 40 50
            return 0;
        }
        ```
3. Pointer based Indexing - Pointer-based indexing ka matlab hai array ke elements ko pointer arithmetic ke through access karna, jisme array ka naam ek pointer hota hai aur *(arr + i) likh ke element milta hai.
   - Example:-
     ```
     #include <stdio.h>
        int main() {
            int arr[5] = {10, 20, 30, 40, 50};
            printf("%d\n", *(arr + 0)); // Output: 10 (first element)
            printf("%d\n", *(arr + 3)); // Output: 40 (fourth element)
            return 0;
        }
        ```
4. Multi-dimensional Indexing - Multi-dimensional indexing ka matlab hai array ke elements ko multiple indices ke through access karna, jaise 2D array me row aur column index use hota hai (arr[i][j]).
    - Example :-
      ```
      #include <stdio.h>
        int main() {
            int mat[3][3] = {
                {1, 2, 3},
                {4, 5, 6},
                {7, 8, 9}
            };
            printf("%d\n", mat[0][2]); // Output: 3 (first row, third column)
            printf("%d\n", mat[2][1]); // Output: 8 (third row, second column)
            return 0;
        }
        ```
5. Pointer to Multi-diamensional Arrays - Pointer to multi-dimensional arrays ka matlab hai multi-dimensional array ke elements ko pointer arithmetic ke through access karna, jisme row aur column ke liye nested dereferencing (*(*(arr+i)+j)) use hota hai.
    - Example :-
      ```
      #include <stdio.h>
        int main() {
            int mat[2][2] = {
                {1, 2},
                {3, 4}
            };
            // Normal indexing
            printf("%d\n", mat[1][0]);   // Output: 3
            // Pointer-based indexing
            printf("%d\n", *(*(mat + 1) + 0)); // Output: 3
            return 0;
        }
        ```

# Traversal in Arrays
Traversal ka matlab hai array ke saare elements ko ek-ek karke sequentially access karna, usually loop ke through, taaki unpe operation perform kiya ja sake (jaise print, search, update).

## Types of Traversal 
1. Forward Traversal - 
2. Backward Traversal
3. Selective Traversal
4. Conditional Traversal
5. Pointer based Traversal













