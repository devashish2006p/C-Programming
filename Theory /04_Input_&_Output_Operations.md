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
scanf()

fscanf()

sscanf()

vscanf()

vfscanf()

vsscanf()

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

