# Definition 
String ek character array hota hai jo ek sequence of characters ko store karta hai aur hamesa null terminator '\0' ka sath end hota hai. C ma koi built-in string type nahi hota, isiliye strings ko *char* array ka form ma implement kiya jata hai. 
# Ways to Initialize Strings in C
  1. Using String Literal 
  char str[] = "Hello";
  2. With Fixed Size and String Literal
  char str[20] = "Hello";
  3. Character Array with Explicit Null Terminator
  char str[] = {'H', 'e', 'l', 'l', 'o', '\0'};
  4. Character Array with Fixed Size and Explicit Null Terminator
  char str[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
  5. Pointer to String Literal
  char *str = "Hello";

# Key Differences Between Strings and Regular Character Arrays

## Null Terminator Requirement
C string ek character array hota hai jo hamesha ek null terminator (`'\0'`) ke saath end hota hai.  
Agar null character missing ho, to wo proper C-type string nahi maana jaata.  

## Automatic Null Character with Literals
Jab string literal use karte ho (jaise `"Hello"`), compiler automatically null terminator add kar deta hai.  
Agar manually character array initialize karte ho, to `'\0'` explicitly add karna padta hai.  

## String-Specific Functions
C strings ke liye kuch specific functions hote hain jaise `strlen()`, `strcpy()`, aur `strcmp()`.  
Ye functions sirf null-terminated character arrays ke liye kaam karte hain, non-null-terminated arrays ke liye nahi.  

# Operations on String 
  1. Traversal – String ke har character ko sequentially access karna.
  
  2. Insertion – Kisi position par naya character dalna.
  
  3. Deletion – Kisi character ko remove karna.
  
  4. Searching – Kisi character ya substring ko find karna.
  
  5. Updating/Modification – Kisi character ki value change karna.
  
  6. Concatenation (Joining) – Do strings ko jodna.
  
  7. Comparison – Do strings ko compare karna.
  
  8. Copying – Ek string ko dusre mein copy karna.
  
  9. Reversing – String ke characters ko ulta karna.
  
  10. Length Calculation – String ki length nikalna (null terminator tak).

# `<string.h>` Functions List
## String Handling Functions
- **strlen()** – Returns the length of a string (excluding `'\0'`).
- **strcpy()** – Copies one string into another.
- **strncpy()** – Copies up to n characters from one string into another.
- **strcat()** – Appends one string to the end of another.
- **strncat()** – Appends up to n characters from one string to another.
- **strcmp()** – Compares two strings lexicographically.
- **strncmp()** – Compares up to n characters of two strings.
- **strchr()** – Finds the first occurrence of a character in a string.
- **strrchr()** – Finds the last occurrence of a character in a string.
- **strstr()** – Finds the first occurrence of a substring in a string.
- **strtok()** – Splits a string into tokens using delimiters.
- **strdup()** – Creates a duplicate copy of a string (POSIX extension).
- **strndup()** – Creates a duplicate copy of up to n characters (POSIX extension).
- **strcoll()** – Compares two strings using locale-specific rules.
- **strxfrm()** – Transforms a string for locale-based comparison.

## Memory Handling Functions
- **memcpy()** – Copies a block of memory from source to destination.
- **memmove()** – Copies memory safely, even if source and destination overlap.
- **memcmp()** – Compares two blocks of memory.
- **memchr()** – Finds the first occurrence of a byte in memory.
- **memset()** – Sets all bytes in a block of memory to a specific value.

---

# Arrays of Strings in C – Detailed Explanation

## 🔹 What is an Array of Strings?
- An **array of strings** is essentially a **two-dimensional character array**.  
- Each row of the 2D array represents one string, and each string is null-terminated (`'\0'`).  
- It allows storing and managing **multiple strings together** in a structured way.

---

## 🔹 Memory Representation
- A **string** in C = `char str[] = "Hello";` → single character array.  
- An **array of strings** = `char arr[3][10] = {"Apple", "Banana", "Mango"};`  
  - Here, `arr` has 3 rows (3 strings), each with space for 10 characters.  
  - Memory layout:  
    ```
    arr[0] → "Apple\0"
    arr[1] → "Banana\0"
    arr[2] → "Mango\0"
    ```

---

##  Ways to Declare Arrays of Strings
1. **Fixed-size 2D array**
   char fruits[3][10] = {"Apple", "Banana", "Mango"};
Stores 3 strings, each up to 9 characters + '\0'.

Array of Pointers to Strings
char *fruits[] = {"Apple", "Banana", "Mango"};
Each element is a pointer to a string literal.

More memory-efficient, but strings are immutable if literals are used.

## Operations on Arrays of Strings
  1. Traversal – Har string ko sequentially access karna.
  
  2. Searching – Kisi specific string ko find karna.
  
  3. Sorting – Strings ko alphabetical order mein arrange karna.
  
  4. Insertion – Nayi string add karna (fixed-size array mein shifting required hoti hai).
  
  5. Deletion – Kisi string ko remove karna.
  
  6. Modification/Updating – Kisi string ki value change karna.
  
  7. Copying – Ek string ko dusre index par copy karna.
  
  8. Concatenation (Joining) – Strings ko jodna (collection ke andar ya external).
  
  9. Length Calculation – Har string ki length nikalna.
  
  10. Reversing – Strings ko ulta karna (individual ya collection order).
