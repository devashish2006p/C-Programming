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
printf()

fprintf()

sprintf()

snprintf()

vprintf()

vfprintf()

vsprintf()

vsnprintf()

---

### Unformatted I/O Functions

These functions deal with **raw data** without formatting.

* Common functions: `getchar()`, `putchar()`, `fread()`, `fwrite()`
* Faster than formatted I/O
* Mostly used for character-level or binary data operations

---

#### Unformatted Input Functions

getchar()

getc()

fgetc()

fgets()

---

#### Unformatted Output Functions

putchar()

putc()

fputc()

fputs()

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

