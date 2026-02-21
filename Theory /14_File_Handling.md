# File Handling in C
File handling in C is the process of creating, opening, reading, writing, and closing files using standard library functions, which allows a program to store and retrieve data permanently from secondary storage devices like a hard disk.

# File handling modes in c

## TEXT MODES 

### r (Read Mode)
Is mode me file sirf read (padhne) ke liye open hoti hai.  
File pehle se exist karni chahiye, warna NULL return karega.  
File pointer shuru se start hota hai.  
Is mode me aap file me likh nahi sakte.

---

### w (Write Mode)

Is mode me file likhne ke liye open hoti hai.  
Agar file pehle se exist karti hai to uska pura purana data delete ho jata hai (truncate ho jata hai).  
Agar file exist nahi karti to nayi file create ho jati hai.  
File pointer start se begin hota hai.

---

###  a (Append Mode)

Is mode me file me data end me add hota hai.  
Agar file exist nahi karti to nayi file create ho jati hai.  
Purana data delete nahi hota.  
File pointer hamesha file ke end me hota hai.

---

###  r+ (Read + Write Mode)

Is mode me file ko read aur write dono kar sakte hain.  
File pehle se exist karni chahiye.  
File pointer beginning se start hota hai.  
Data overwrite ho sakta hai agar same jagah likha jaye.

---

### w+ (Read + Write with Truncate)

Is mode me read aur write dono allowed hain.  
Agar file exist karti hai to pura purana data delete ho jata hai.  
Agar file exist nahi karti to nayi file create hoti hai.  
File pointer start se hota hai.

---

###  a+(Read + Append Mode)

Is mode me read aur write dono allowed hain.  
Writing hamesha file ke end me hoti hai.  
File exist na ho to create ho jati hai.  
Reading kahin se bhi ho sakti hai, lekin writing sirf end me hogi.

---

## BINARY MODES (6)

Binary mode me b lagaya jata hai. Ye mostly Windows me important hota hai. Linux me text aur binary me zyada difference nahi hota.

---
### rb

Ye binary read mode hai.  
File exist karni chahiye.  
Sirf binary data read karne ke liye use hota hai (jaise images, executables).

---

### wb

Binary write mode hai.  
Agar file exist kare to purana data delete ho jata hai.  
Agar file exist na kare to nayi create hoti hai.  
Binary data likhne ke liye use hota hai.

---

### ab

Binary append mode hai.  
Data hamesha file ke end me add hota hai.  
Purana data safe rehta hai.  
File exist na kare to create hoti hai.

---

### rb+

Binary read + write mode hai.  
File exist karni chahiye.  
Data read bhi kar sakte hain aur overwrite bhi kar sakte hain.

---

### wb+

Binary read + write mode hai.  
Agar file exist kare to purana data delete ho jata hai.  
Agar exist na kare to create hoti hai.  
Binary data ke liye use hota hai.

---

### ab+

Binary read + append mode hai.  
Reading allowed hai.  
Writing hamesha file ke end me hoti hai.  
File exist na kare to create hoti hai.

# File Handling Functions in C
1. fopen()
File ko specified mode me open karta hai.
Return type FILE* hota hai. Agar file open na ho to NULL return karta hai.

2. fclose()
Open file ko close karta hai.
File close karna important hai taaki resources free ho sakein.

3. fgetc()
File se ek character read karta hai.
EOF milne par EOF return karta hai.

4. fputc()
File me ek character write karta hai.

6. getc()
fgetc() jaisa hi hai. Character read karta hai.

6. putc()
fputc() jaisa hi hai. Character write karta hai.

7. fgets()
File se ek line ya specified length tak string read karta hai.

8. fputs()
File me string write karta hai. Newline automatically add nahi karta.

9. fprintf()
File me formatted output likhta hai (jaise printf file ke liye).

10. fscanf()
File se formatted input read karta hai (jaise scanf file ke liye).

11. fread()
Binary data ko file se read karta hai.
Mostly structures, images, objects ke liye use hota hai.

12. fwrite()
Binary data ko file me write karta hai.

13. fseek()
File pointer ko specified location par move karta hai.

14. ftell()
Current file pointer position batata hai.

15. rewind()
File pointer ko beginning me le jata hai.

16. feof()
Check karta hai ki end of file reach hua hai ya nahi.

17. ferror()
Check karta hai ki file operation me error aaya ya nahi.

18. clearerr()
File ke error indicators ko clear karta hai.

19. fflush()
Output buffer ko forcefully file me write karta hai.

20. setbuf()
File ke buffer ko control karta hai.

21. setvbuf()
Buffering mode ko detail me control karta hai.

22. remove()
File delete karta hai.

23. rename()
File ka naam change karta hai.

24. tmpfile()
Temporary file create karta hai.

25. tmpnam()
Temporary file name generate karta hai.

26. perror()
Error message print karta hai (last error ke according).

# File Operations in C

File operations in C input/output tasks perform karne ke liye use hote hain. Inki help se hum files me data read, write, append aur manage kar sakte hain. Yeh data store karne aur retrieve karne ke liye bahut important concept hai.

## Reading from a File

File se data read karna ek basic aur important operation hai. C me multiple functions available hote hain jo text aur binary dono type ke data ko read kar sakte hain.

- `fgetc()` ek single character read karta hai file se.
- `fgets()` ek line ya limited number of characters read karta hai.
- `fread()` binary data ko buffer me read karta hai.

Reading ke time par end-of-file aur errors handle karna zaruri hota hai.

---

## Writing to a File

File me data likhne ke liye alag-alag functions use kiye jate hain. Yeh text aur binary dono format me writing support karte hain.

- `fputc()` ek single character write karta hai.
- `fputs()` ek string write karta hai.
- `fwrite()` binary data buffer se file me write karta hai.

Writing karte waqt file ka mode sahi select karna important hota hai.

---

## Appending Data to a File

Append ka matlab hota hai existing data ko overwrite na karte hue file ke end me naya data add karna.

Iske liye file ko append mode (`"a"` ya `"ab"`) me open kiya jata hai. Is mode me jitni bhi writing hoti hai, wo automatically file ke end me add hoti hai.

Yeh tab useful hota hai jab hume logs ya continuous records maintain karne ho.

---

## File Error Handling

File handling me error handling bahut important concept hai. Unexpected situations jaise file na milna, permission issue, ya read/write failure ko handle karna zaruri hota hai.

- File open karte waqt check karna chahiye ki file pointer NULL to nahi hai.
- Read ya write ke baad error check karne ke liye `ferror()` aur `feof()` use kiye jate hain.
- File ko properly `fclose()` karna zaruri hota hai taaki resource leak na ho aur data corruption na ho.

Proper error handling program ko stable aur secure banata hai.

# Text File aur Binary File in C

## Text File kya hota hai?

Text file wo file hoti hai jisme data human-readable form me store hota hai.  
Isme characters (letters, numbers, symbols) ASCII ya Unicode format me save hote hain.

- Data easily Notepad jaise editor me read kiya ja sakta hai.
- Har line ke end me newline character (`\n`) hota hai.
- Numbers bhi character form me store hote hain.
- Size comparatively zyada ho sakta hai.
- Text mode me file open ki jati hai: `"r"`, `"w"`, `"a"`.

Examples:
- `.txt`
- `.csv`
- `.c`
- `.html`

---

## Binary File kya hota hai?

Binary file me data machine-readable raw format me store hota hai.  
Isme data direct memory representation me likha jata hai.

- Human readable nahi hota.
- Fast read/write hota hai.
- Exact memory copy store hoti hai.
- Binary mode me file open hoti hai: `"rb"`, `"wb"`, `"ab"`.

Examples:
- `.exe`
- `.dat`
- `.bin`
- Images (`.jpg`, `.png`)
- Audio/Video files

---

## Main Difference

| Text File | Binary File |
|------------|------------|
| Human readable | Human readable nahi |
| Characters form me store | Raw memory form me store |
| Size thoda zyada | Size comparatively kam |
| Thoda slow | Fast |

---
