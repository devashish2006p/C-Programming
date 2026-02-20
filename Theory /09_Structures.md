# Structures in C 
Structure ek **user-defined data type** hai jo alag-alag data types ke variables ko ek hi naam ke under group karta hai.  
Matlab ek hi "container" ke andar tum `int`, `float`, `char[]` jaise different types ke data ek saath store kar sakte ho.  
Ye arrays se alag hai kyunki arrays sirf ek hi type ke elements store karte hain, jabki structures heterogeneous data store karte hain.

## Syntax
```
struct Student {
    int roll;        // integer member
    char name[50];   // character array member
    float marks;     // float member
};
```
### Syntax Breakdown
Keyword struct - Ye batata hai ki tum ek structure define kar rahe ho. Har structure ka apna naam hota hai (yahan Student).

Structure Name (Student) - Ye ek identifier hai jo tumhare structure ko represent karta hai. Isse tum baad mein variables declare kar sakte ho.

Curly Braces { ... } - Iske andar tum members define karte ho. Har member ek variable hota hai jo alag data type ka ho sakta hai.

Members (Variables) - int roll; → ek integer member. char name[50]; → ek character array member (string store karne ke liye). float marks; → ek floating-point member. Har member apna separate memory block occupy karta hai.

Semicolon ; at the end - Structure definition ke baad semicolon mandatory hai. Ye compiler ko batata hai ki structure definition complete ho gayi hai.

# Structures Members – Initialization and Access in C

## Initialization Methods (Ways to Initialize Members)

1. **Direct Initialization at Declaration (Designated Initialization)**
   ```
   struct Student {
       int roll;
       char name[50];
       float marks;
   };
   struct Student s1 = {101, "Rahul", 89.5};
   ```
Members ko declaration ke time par hi values assign kar di jaati hain.

2. Partial Initialization
struct Student s2 = {102}; 
Sirf pehle member ko initialize kiya, baaki members automatically default (0 ya '\0') ho jaate hain.

3. Designated Initializers 
struct Student s3 = {.roll = 103, .marks = 92.0};
Specific members ko initialize karna possible hai, order follow karna zaroori nahi.

4. Runtime Assignment
struct Student s4;
s4.roll = 104;
strcpy(s4.name, "Amit");
s4.marks = 85.0;
Members ko baad mein assign kiya jaata hai.

5. Using Functions
void initStudent(struct Student *s, int r, char *n, float m) {
    s->roll = r;
    strcpy(s->name, n);
    s->marks = m;
}
Initialization ek helper function ke through bhi kiya ja sakta hai.

##  Access Methods (Ways to Access Members)
1. Dot Operator (.)
s1.roll;
s1.marks;
Direct access jab tumhare paas structure variable ho.

2. Arrow Operator (->)
struct Student *ptr = &s1;
ptr->roll;
ptr->marks;
Jab tum pointer ke through structure ko access karte ho.

3. Array of Structures
struct Student arr[3];
arr[0].roll = 105;
Array ke index ke saath dot operator use hota hai.

4. Pointer Arithmetic with Arrays of Structures
(arr+1)->marks = 90.0;
Array ke pointer ke through arrow operator use karke access karna.

5. Function Parameters
Members ko function ke andar access karna:
void printStudent(struct Student s) {
    printf("%d %s %f", s.roll, s.name, s.marks);
}

# Nested Structures in C
- **Nested Structure** ka matlab hai ek structure ke andar dusra structure ko member ke roop mein include karna.  
- Ye tab use hota hai jab ek complex entity ko represent karna ho jo multiple sub-entities rakhta hai.  
- Matlab ek "structure of structures" ban jaata hai.

## Use (Purpose)
- **Data Organization**: Complex data ko logically group karna.  
- **Real-world Modeling**: Jaise ek Student ke andar Address details bhi store karna.  
- **Code Reusability**: Ek structure ko alag define karke dusre mein reuse karna.  
- **Hierarchical Data Representation**: Jab ek entity ke andar sub-entities ho (Employee → Address, Date of Birth).  

##  Syntax
```
struct Address {
    char city[20];
    int pin;
};

struct Student {
    int roll;
    char name[50];
    float marks;
    struct Address addr;   // Nested structure member
};
```
### Syntax Breakdown
    1. Outer Structure (Student)
    
    2. Ye main entity ko represent karta hai (Student record).
    
    3. Inner Structure (Address)
    
    4. Ye ek sub-entity hai jo Student ke andar embedded hai.
    
    5. Member Declaration (struct Address addr;)
    
    6. Outer structure ke andar inner structure ko ek member ke roop mein declare kiya gaya hai.
    
    7. Matlab har Student ke paas ek Address bhi hoga.
    
### Accessing Nested Members
```
struct Student s1;
s1.roll = 101;
strcpy(s1.name, "Rahul");
s1.marks = 89.5;

strcpy(s1.addr.city, "Patna");  // Access nested structure member
s1.addr.pin = 800001;
```


