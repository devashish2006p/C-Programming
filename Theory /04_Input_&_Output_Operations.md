# Input and Output (I/O) Operations in C

---

## Introduction to I/O Operations

In C programming, **Input and Output (I/O) operations** are used so that a program can **communicate with users and external sources** like files.

* **Input**: Taking data from the user or files into the program.
* **Output**: Displaying results on the screen or storing data into files.

Without I/O operations, programs would only perform internal calculations and would not be useful in real life.

---

## Importance of Input and Output in Programming

I/O operations are important because:

* **User Interaction**: Users can give input and see output results.
* **Data Management**: Programs can save data in files and read it later.
* **Decision Making**: Programs can take decisions based on user input.

---

## C provides two types of I/O functions:

### Formatted I/O Functions

These functions allow data to be displayed or read in a **well-structured format**.

* Common functions: `printf()`, `scanf()`
* Uses **format specifiers** like `%d`, `%f`, `%c`
* Easy to read and user-friendly

Example:

```c
printf("Age: %d", age);
```

#### Formatted Input Functions
- scanf() : It is a function in C that reads input from keyboard. It stores the input into variables based on the format specifiers. You must give the address of the variable using '&' so that the value can be stored correctly. It returns the number of inputs that were successfully read.
  - Ex :
    ```
    #include <stdio.h>
    int main() {
    int age;
    printf("Enter your age: ");
    scanf("%d", &age);   // Reads an integer from keyboard
    printf("You entered: %d\n", age);
    return 0;
    }
    ```

- fscanf() : It reads formatted input from a file intstead of the keyboard. It works just like *scanf()*, but the soruce of data is a file stream opened using *fopen()*.

  ```
  - #include <stdio.h>
    int main() {
    FILE *fp = fopen("data.txt", "r");   // open file in read mode
    int num;
    fscanf(fp, "%d", &num);              // read integer from file
    printf("Number: %d\n", num);
    fclose(fp);                          // close file
    return 0;
    }
    ```

- sscanf() : It reads formatted input from a string instead of the keyboard or a file. It works just like scanf(), but the source of data is a string buffer.
    - Example : -
  ```
    #include <stdio.h>
    int main() {
    char str[] = "123 45.67";
    int x; float y;
    sscanf(str, "%d %f", &x, &y);
    printf("Integer: %d, Float: %.2f\n", x, y);
    return 0;
    }
  ```

- vscanf() : It reads formatted input from the keyboard, but instead of normal arguments, it uses a *va_list (variable argument list)*. This makes it useful when you don't know in advance how many arguments will be passed. User must have initialize *va_list* using *va_start* and clean it with *va_end*.
    - Example :
```
#include <stdio.h>
#include <stdarg.h>

void myInput(const char *format, ...) {
    va_list args;
    va_start(args, format);
    vscanf(format, args);   // uses vscanf internally
    va_end(args);
}

int main() {
    int x; float y;
    printf("Enter an integer and a float: ");
    myInput("%d %f", &x, &y);
    printf("Integer: %d, Float: %.2f\n", x, y);
    return 0;
}

```

- vfscanf() - It reads formatted input from a file, but instead of normal arguments it uses a *va_list*. 

  - Rules :
    1. File must be opened first → You must open the file using fopen()         before using vfscanf().

    2. Pass the file pointer → The first argument must be the file              pointer (FILE *fp).

    3. Use format specifiers correctly → Tell vfscanf() what type of            data to read (%d, %f, %s, etc.).

    4. Arguments handled by va_list → Instead of normal arguments, you          must use a va_list created with <stdarg.h> macros (va_start,             va_end).

    5. Return value → It returns the number of items successfully read          from the file.

    6. Close the file → Always close the file with fclose() after               reading.
    Example :
```
#include <stdio.h>
#include <stdarg.h>

void myFileInput(FILE *fp, const char *format, ...) {
    va_list args;
    va_start(args, format);
    vfscanf(fp, format, args);   // uses vfscanf internally
    va_end(args);
}

int main() {
    FILE *fp = fopen("info.txt", "r");
    int id; char name[20];
    myFileInput(fp, "%d %s", &id, name);
    printf("ID: %d, Name: %s\n", id, name);
    fclose(fp);
    return 0;
}
```

- vsscanf() : It reads formatted input from a string but instead of normal arguments, it uses a *va_list*.
  - Rules :-
    1. Input source is always a string, not keyboard or file.
    2. Format specifiers must match the type of data inside the string.
    3. Instead of normal arguments, you must use a *va_list*.
    4. Function returns the number of items successfully read.
    5. Useful for custom parsing functions where arguments are not fixed.

    Example :
```
#include <stdio.h>
#include <stdarg.h>

void myStringInput(const char *str, const char *format, ...) {
    va_list args;
    va_start(args, format);
    vsscanf(str, format, args);   // uses vsscanf internally
    va_end(args);
}

int main() {
    char data[] = "101 Santosh 89.5";
    int id; char name[20]; float marks;
    myStringInput(data, "%d %s %f", &id, name, &marks);
    printf("ID: %d, Name: %s, Marks: %.2f\n", id, name, marks);
    return 0;
}

```
---

#### Formatted Output Functions 
printf() - It is used to print formatted output on the screen. 

  - Syntax : int printf(const char *format, ...);
      - int = It is a return type
      - printf = Function name
      - const char *format = parameters, it contains normal text + format specifiers
      - ... = These are the variable arguments.
   
  - Example :
    ```
    #include <stdio.h>
    int main() {
    int age = 22;
    char name[] = "Santosh";

    printf("Name: %s, Age: %d\n", name, age);
    return 0;
    }
    ```

fprintf() - It is used to print formatted output into a file or stream. 

  - Syntax : int fprintf(FILE *stream, const char *format, ...);
      - Breakdown :-
          - int = Return type
          - fprintf = Function
          - *FILE stream = Target File pointer
          - *const chart format = format specifiers
          - ... (ellipsis) = variable argument
       
    - Example :
```
#include <stdio.h>
int main() {
    FILE *fp;
    fp = fopen("output.txt", "w");   // open file in write mode

    int age = 25;
    char name[] = "Santosh";

    // Write formatted output into the file
    fprintf(fp, "Name: %s, Age: %d\n", name, age);

    fclose(fp);   // close the file
    return 0;
}
```

sprintf() - It writes formatted output into a string (character array) instead of printing it on the screen. It works like printf(), but the result is stored in a buffer you provide. 

  - Syntax : int sprintf(char *str, const cahr *format, ...);
      Breakdown :
        - int = return type
        - sprintf = function name
        - *char str = target string
        - *const char format = format string
        - ... (ellipsis) = variable arguments. 
  - Example
```
#include <stdio.h>
int main() {
    char buffer[100];
    int age = 25;
    char name[] = "Santosh";

    // Store formatted output into buffer
    sprintf(buffer, "Name: %s, Age: %d", name, age);

    // Print the buffer content
    printf("%s\n", buffer);

    return 0;
}
```
snprintf() - It is a safer version of *sprintf()* that writes formatted output into a string but also limits the number of characters written. It prevents buffer overflow by specifying the maximum size of the target buffer. 
- Syntax : int snprintf(char *str, size_t size, const char *format, ...);
    - Breakdown :
      - int = return type
      - snprintf = function name
      - *char str = target string
      - size_t size = maximum number of characters to write
      - *const char format = format specifiers
      - ... (ellipsis) = variable arguments. 
- Example
```
#include <stdio.h>

int main() {
    char buffer[20];
    int age = 25;
    char name[] = "Santosh";

    // Safe formatted output into buffer
    snprintf(buffer, sizeof(buffer), "Name: %s, Age: %d", name, age);

    // Print the buffer content
    printf("%s\n", buffer);

    return 0;
}
```
vprintf() - It prints formattted output to the standard output using a *va_list* of arguments. It is mainly used inside functions that handle variable arguments indireclty. 

  - Syntax : int vprintf(const char *format, va_list arg); 
      - Breakdown
          - int = return type
          - vprintf = function name
          - *const char format = format specifiers
          - va_list arg = argument list
  - Example
```
#include <stdio.h>
#include <stdarg.h>

// Custom function using vprintf
void display(const char *format, ...) {
    va_list args;
    va_start(args, format);   // initialize va_list
    vprintf(format, args);    // use vprintf to print
    va_end(args);             // clean up
}

int main() {
    display("Name: %s, Age: %d\n", "Santosh", 25);
    return 0;
}
```

vfprintf() - It prints formatted output into a file stream using a va_list of arguments. It is mainly used inside functions that handle variable arguments indirectly and want to write output to a file. 
  - syntax : int vfprintf(FILE *stream, const char *format, va_list arg);
      - Breakdown
          - int = return type
          - vfprintf = function name
          - *File stream = target file pointer
          - *const char format = format specifiers
          - va_list arg = argument list 
  - Example
```
#include <stdio.h>
#include <stdarg.h>

// Custom function using vfprintf
void logToFile(FILE *fp, const char *format, ...) {
    va_list args;
    va_start(args, format);        // initialize argument list
    vfprintf(fp, format, args);    // write formatted output to file
    va_end(args);                  // clean up
}

int main() {
    FILE *fp = fopen("log.txt", "w");   // open file in write mode

    logToFile(fp, "Name: %s, Age: %d\n", "Santosh", 25);

    fclose(fp);   // close the file
    return 0;
}
```
vsprintf() - It writes formatted output into a string using a *va_list* of arguments. It works like *sprintf()* but instead of variable arguments (...), it uses a *va_list* for indirect argument handling. 

  - Syntax : int vsprintf(char *str, const char *format, va_list arg);
      - Breakdown
          - int = return type
          - vsprintf = function name
          - *char str = target string
          - *const char format = format string
          - va_list arg = argument list 
  - Example
```
#include <stdio.h>
#include <stdarg.h>

// Custom function using vsprintf
void makeString(char *buffer, const char *format, ...) {
    va_list args;
    va_start(args, format);          // initialize argument list
    vsprintf(buffer, format, args);  // write formatted output into buffer
    va_end(args);                    // clean up
}

int main() {
    char buf[100];
    makeString(buf, "Name: %s, Age: %d", "Santosh", 25);

    printf("%s\n", buf);   // print the stored string
    return 0;
}
```
vsnprintf() - It writes formatted output into a string using a *va_list* of arguments, but with a size limit. It is the safer version of *vsprintf()* because it prevents buffer overflow by restricting the maximum number of characters written. 

  - Syntax : int vsnprintf(char *str, size_t size, const char *format, va_list arg);

      - Breakdown
          - int = return type
          - vsnprintf = function name
          - *char str = target string
          - size_t size = maximum number of characters to write
          - *const char format = format specifiers
          - va_list arg = argument list
  - Example
```
#include <stdio.h>
#include <stdarg.h>

// Custom function using vsnprintf
void makeSafeString(char *buffer, size_t size, const char *format, ...) {
    va_list args;
    va_start(args, format);                 // initialize argument list
    vsnprintf(buffer, size, format, args);  // safe formatted output into buffer
    va_end(args);                           // clean up
}

int main() {
    char buf[30];
    makeSafeString(buf, sizeof(buf), "Name: %s, Age: %d", "Santosh", 25);

    printf("%s\n", buf);   // print the stored string
    return 0;
}

```
---

### Unformatted I/O Functions

These functions deal with **raw data** without formatting.

* Common functions: `getchar()`, `putchar()`, `fread()`, `fwrite()`
* Faster than formatted I/O
* Mostly used for character-level or binary data operations

---

#### Unformatted Input Functions

getchar() - It is a standard input function that reads a **single character** from the input stream (stdin). - It returns the character as an `int` (ASCII value).
  - Syntax:-
    int getchar(void);
    - Breakdown :-
      int -> return type
      getchar -> function name
      void -> takes no arguments
  - Example :-
```
#include <stdio.h>

int main() {
    char ch;
    printf("Enter a character: ");
    ch = getchar();   // reads one character
    printf("You entered: %c\n", ch);
    return 0;
}
```

getc() - It is a standard input/output function in C that reads the **next character** from a specified file stream. - It returns the character as an `int` (ASCII value), or `EOF` if the end of file is reached or an error occurs.

  - Syntax :-
    int getc(FILE *stream);
    - Breakdown:-
      int -> return type
      getc -> function name
      *File stream -> pointer to a file object (obtained using fopen) from which the character is read.
  - Example :-
```
#include <stdio.h>

int main() {
    FILE *fp = fopen("example.txt", "r"); // open file in read mode
    int ch;

    if (fp == NULL) {
        printf("Error opening file.\n");
        return 1;
    }

    while ((ch = getc(fp)) != EOF) {  // read characters until EOF
        putchar(ch);                  // print each character
    }

    fclose(fp);
    return 0;
}
```
      
fgetc() - It is a standard I/O function in C that reads the **next character** from a given file stream. - It returns the character as an `int` (ASCII value), or `EOF` if the end of file is reached or an error occurs.
  - Syntax :-
    int fgetc(FILE *stream);
      - Breakdown :-
          - int -> return type
          - fgetc -> function name
          - *FILE stream -> point to a file object from which the character is read. 
  - Example :-
```
#include <stdio.h>

int main() {
    FILE *fp = fopen("example.txt", "r"); // open file in read mode
    int ch;

    if (fp == NULL) {
        printf("Error opening file.\n");
        return 1;
    }

    while ((ch = fgetc(fp)) != EOF) {  // read characters until EOF
        putchar(ch);                   // print each character
    }

    fclose(fp);
    return 0;
}
```

---

#### Unformatted Output Functions

putchar() - It is a standard output function in C that writes a **single character** to the output stream (stdout). - It returns the character written as an `int`, or `EOF` if an error occurs.
  - Syntax :-
    int putchar(int char);
    - Breakdown:-
        - int -> return type
        - putchar -> function name
        - int char -> the characterto be printed
  - Example:-
```
#include <stdio.h>

int main() {
    char ch = 'A';
    putchar(ch);   // prints 'A' to the screen
    putchar('\n'); // prints a newline
    return 0;
}
```
putc() - It is a standard output function in C that writes a **single character** to a specified file stream. - It returns the character written as an `int`, or `EOF` if an error occurs.
  - Syntax :-
    int putc(int char, FILE *stream);
    - Breakdown :-
      - int -> return type
      - putc -> function name
      - int char -> The character to be written
      - *File Stream -> point to the file object where the character will be written.
  - Example :-
```
#include <stdio.h>

int main() {
    FILE *fp = fopen("output.txt", "w"); // open file in write mode
    if (fp == NULL) {
        printf("Error opening file.\n");
        return 1;
    }

    putc('H', fp);   // writes 'H' to the file
    putc('i', fp);   // writes 'i' to the file
    putc('\n', fp);  // writes newline to the file

    fclose(fp);
    return 0;
}
```

fputc() - It is a standard output function in C that writes a **single character** to a specified file stream. - It returns the character written as an `int`, or `EOF` if an error occurs.

  - Syntax:-
    int fputc(int char, FILE *stream);
    - Breakdown :-
      int -> return type
      fputc -> function name
      int char -> the character to be written
      *File stream -> point to the file object where the character will be written. 
  - Example
```
#include <stdio.h>

int main() {
    FILE *fp = fopen("output.txt", "w"); // open file in write mode
    if (fp == NULL) {
        printf("Error opening file.\n");
        return 1;
    }

    fputc('H', fp);   // writes 'H' to the file
    fputc('e', fp);   // writes 'e' to the file
    fputc('y', fp);   // writes 'y' to the file
    fputc('\n', fp);  // writes newline to the file

    fclose(fp);
    return 0;
}
```
fputs() - It is a standard output function in C that writes a **string of characters** to a specified file stream. - It returns a non-negative value on success, or `EOF` if an error occurs.
  - Syntax :-
    int fputs(const char *str, FILE *stream);
    - Breakdown :-
        - int -> return type
        - fputs -> function name
        - *const char str -> pointer to the string that will be written.
        - *File stream -> point to the file object where the string will be written.
  - Example :-
```
#include <stdio.h>

int main() {
    FILE *fp = fopen("output.txt", "w"); // open file in write mode
    if (fp == NULL) {
        printf("Error opening file.\n");
        return 1;
    }

    fputs("Hello, World!\n", fp);  // writes the string to the file
    fputs("This is written using fputs().\n", fp);

    fclose(fp);
    return 0;
}
```
---

### Common Format Specifiers

| Specifier   | Use                         |
| ----------- | --------------------------- |
| `%d` / `%i` | Integer                     |
| `%f`        | Floating point              |
| `%.2f`      | Float with 2 decimal places |
| `%c`        | Character                   |
| `%s`        | String                      |
| `%x`        | Hexadecimal                 |
| `%o`        | Octal                       |
| `%p`        | Address                     |
| `%e`        | Scientific notation         |

---

### Common Input Specifiers

| Specifier | Data Type |
| --------- | --------- |
| `%d`      | Integer   |
| `%f`      | Float     |
| `%c`      | Character |
| `%s`      | String    |

---

## Common Errors and Solutions

1. **Wrong format specifier**  
This error happens when the format specifier does not match the variable type, so always use the correct specifier like `%d` for integers and `%f` for floating-point values.

2. **Buffer overflow**  
Buffer overflow occurs when input data is larger than the allocated memory, so always limit the input size to prevent memory corruption.

3. **Whitespace issue**  
Whitespace issues happen when input functions stop reading at spaces, so using `fgets()` helps read the full line including spaces.

4. **File not found**  
This error occurs when the program tries to open a file that does not exist or has no permission, so always check if the file exists before using it.

5. **EOF error**  
EOF errors occur when the program keeps reading after the end of a file, so checking function return values helps stop reading at the correct time.


---

## Input Validation Techniques

### Range Checking
Range checking is a validation technique where the program ensures that the input value lies within a predefined minimum and maximum limit before processing it, such as verifying whether an age is between 0 and 120.

### Checking `scanf()` Return Value
Checking the return value of `scanf()` helps confirm whether the expected number of inputs were successfully read, because `scanf()` returns the count of correctly assigned values, allowing detection of invalid input.

### Limiting String Size
Limiting string size prevents buffer overflow by restricting the number of characters read into a character array, for example using `%19s` to safely read input into a 20-character buffer.

### File NULL Check
A file NULL check is performed after calling `fopen()` to verify that the file was opened successfully, since `fopen()` returns `NULL` if the file does not exist or access is denied.

---

## Best Practices for I/O

* Use clear prompts
* Always check return values
* Limit input size
* Close files after use
* Use loops for valid input

---

## Advanced I/O – File Handling

File I/O allows data to be stored permanently.

### Basic File Operations

1. Open file – `fopen()`
2. Read/Write – `fprintf()`, `fscanf()`
3. Close file – `fclose()`

---

### File Modes

#### 1. `"r"` – Read Mode

This mode is used to **read data from a file**.

- File **must already exist**
- File opens in **read-only**
- Cursor starts from the **beginning**
- If file does not exist → opening fails

**Use case:**  
Reading data from an existing file.

---

#### 2. `"w"` – Write Mode

This mode is used to **write data into a file**.

- If file exists → **old data is erased**
- If file does not exist → **new file is created**
- Cursor starts from the **beginning**
- Write-only mode

**Use case:**  
Creating a new file or overwriting old data.

---

#### 3. `"a"` – Append Mode

This mode is used to **add data at the end of a file**.

- File is created if it does not exist
- Old data is **not deleted**
- Cursor always moves to the **end**
- Write-only mode

**Use case:**  
Adding logs or new records without removing old data.

---

#### 4. `"r+"` – Read and Write Mode

This mode allows **both reading and writing**.

- File **must exist**
- Cursor starts from the **beginning**
- Data can be read and modified

**Use case:**  
Updating existing file data.

---

#### 5. `"w+"` – Write and Read Mode

This mode allows **reading and writing**, but with reset.

- If file exists → **content is erased**
- If file does not exist → new file is created
- Cursor starts from the beginning

**Use case:**  
Create a fresh file and then read/write.

---

#### 6. `"a+"` – Append and Read Mode

This mode allows **reading and appending**.

- File created if it does not exist
- Writing happens only at the **end**
- Reading can be done from anywhere

**Use case:**  
Reading old data and adding new data safely.

---

## File I/O Example

```c
FILE *fp = fopen("data.txt", "w");
fprintf(fp, "Hello World");
fclose(fp);
```

---

