# 1. Linked List
Ya ek data structure hai jisme elements memory ma continuous store nhi hota, balki har node apne next node ka address store karke unse linked rehta hai. Ishme har nodes ka 2 parts hote hai ek Data part aur dusra Link/Pointer Part. 
- Ex:-
```
Node 1:
Data = 10
Next = Address of Node 2

Node 2:
Data = 20
Next = Address of Node 3

Node 3:
Data = 30
Next = NULL
```
# 2. Advantages
1. Dynamic Size - Linked list ka size pehle sa fix nhi karna parta. zarurat parne par naye nodes runtime par add kiye jaa shakta hai.
2. Easy Insertion - Ksi position par naya node add karne ka lia sirf pointers update karne hote hai to poora data shift nahi karna parta.
3. Easy Deletion - Node delete karne ka liye baaki elements ko move nahi karna parta, sirf links change karne hote hai.
4. Non - Contiguous Memory - Nodes memory ma alag-alag jagha par store ho shakta hai. Continuous memory block ki zarurat nahi hoti.
5. Memory Utilization - Jitna nodes cahiye utni hi memory allocate hoti hai, isiliye fixed size array ki tarah extra memory waste nahi hoti.

# 3. Disadvantage
1. Extra Memory Requirement - Har node ma data ka sath pointer bhi store karna parta hai, jisshe extra memory consume hoti hai.
2. No Random Access - Array ki tarah direct index access nahi kar shakte. Ksi node tak pahunchne ka lia starting sa traverse karna parta hai.
3. Slow Searching - Agr node ka address nahi pata to sequentially ek ek node check karna parta hai.
4. Pointer Management Complexity - Pointers ko sahi maintain karna parta hai. Galti hone par memory leaks ya broken links ho shakte hai.
5. Poor Cache Performance - Nodes memory ma scattered hote hai, isiliye CPU cache ka fayda array ka comparision ma kam milta hai.

# 4. Types of Linked List
1. Singly Linked List (SLL) - Singly Linked List ek linear data structure hai jisme har node me ek data field aur ek next pointer hota hai. Next pointer agle node ka address store karta hai.
   - Characteristics
       - Sirf forward direction ma traverse kar shakta hai.
       - Har node ko apne next node ka hi pata hota hai.
       - Memory requirement relatively kam hota hai.
2. Doubly Linked List (DLL) - Doubly Linked List ek linked list hai jisme har node me data ke saath do pointers hote hain: ek previous node ke liye aur ek next node ke liye.
   - Characteristics
     - Forward aur backward dono direction ma traverse kar shakte hai.
     - Har node ko apne previous aur next dono nodes ka pata hota hai.
     - Pointer extra hone ki wajah sa memory zyada lagti hai.
       
3. Circular Singly Linked List (CSLL) - Circular Singly Linked List me last node ka next pointer NULL ko point nahi karta, balki first node ko point karta hai.
   - Characteristics
       - Koi NULL pointer nahi hota.
       - Last node aur first node connected hote hai.
       - List circular chain ban jati hai.
       - Repeated traversal ka liye useful hoti hai.
4. Circular Doubly Linked List (CDLL) - Circular Doubly Linked List me har node ke paas previous aur next pointers hote hain, aur first aur last nodes ek dusre se circularly connected hote hain.
   - Characteristics
       - Forward aur backward dono traversal possible hai.
       - First node ka previous last node ko point karta hai.
       - Last node ka next first node ko point karta hai.
       - Koi NULL pointer nahi hota.
5. Header Linked List - Header Linked List ek special linked list hai jisme list ke beginning me ek extra node (Header Node) rakha jata hai jo actual user data store nahi karta, balki list ke baare me information store karta hai. Ya total number of nodes, first node ka address, list ki metadata information ya sab store kar shakta hai.
   - Characteristics
       - List operations ko simplify karta hai.
       - Empty list handle karna easy ho jata hai.
       - Advanced implementations ma use hota hai.

# 5. Terminologies of Linked List
1. Node - Ya LL ki sbse choti building block unit hoti hai. Purni LL nodes sa milkar banti hai. Ex - 10 -> 20 -> 30 -> NULL, yahan 10 ek node hai, 20 ek node hai, 30 ek node hai yani total 3 nodes hai. Linked list nodes ki chain hoti hai, node khud linked list nahi hota. 
   - **Internal structure of a Node**
     - Ek basic node ka 2 parts hote hai. Data and Next.
     - Data field : actual value store karta hai.
     - Linked Field : Agle node ka address store karta hai.
2. Next Pointer - Singly linked list ma jo pointer next node ko point karta hai usshe next pointer kehte hai.
3. Previous Pointer - Ya doubly Doubly Linked List ma hota hai joki previous node ko point kar rha hota hai.
4. Head Pointer - Linked list ka first node ka address store karne wale pointer ko Head pointer kehte hai.
5. Tail Pointer - Last node ko point karne wale pointer ko Tail Pointer kehte hai.
6. NULL Pointer - Ishka mtlb hota hai no address mtlb aage koi node exist nhi karta.

# 6. Linked List Traversal 
**Traversal** ka matlab hota hai linked list ke har node ko **ek-ek baar visit/access karna**.

---

## 6.1 Purpose
Traversal ka use hota hai:
- Data print karna
- Data search karna
- Sum nikalna
- Count nikalna
- Maximum/Minimum find karna
- Kisi condition ko check karna

> **Note:** Traversal sirf nodes ko visit karta hai, structure ko modify nahi karta.

---

## 6.2 Traversal Logic

1. Head se start karo.
2. Ek temporary pointer (`temp`) banao.
3. `temp = head`
4. Jab tak `temp != NULL`
   - Current node ka data access karo.
   - `temp = temp->next`
5. `temp` NULL hote hi traversal khatam.

---

## 6.3 Syntax

```c
struct node *temp = head;

while(temp != NULL)
{
    // Process current node

    temp = temp->next;
}
```

---

## 6.4 Diagram

```text
head
 ↓
[10|•] → [20|•] → [30|•] → [40|NULL]

temp
 ↓

Iteration 1
10

Iteration 2
20

Iteration 3
30

Iteration 4
40

Iteration 5
NULL (Stop)
```

---

## 6.5 Time Complexity

| Case | Complexity |
|------|------------|
| Best Case | O(n) |
| Average Case | O(n) |
| Worst Case | O(n) |

> Har node ko ek baar visit karna padta hai.

---

## 6.6 Space Complexity

```
O(1)
```

Sirf ek temporary pointer use hota hai.

---

## 6.7 Important Points

- Traversal **head** se start hota hai.
- Original `head` ko change nahi karna chahiye.
- Isliye ek **temporary pointer** use karte hain.
- Last node ke baad `next = NULL` hota hai.
- `temp == NULL` hone par loop stop ho jata hai.

---

## 6.8 Common Applications

- Display linked list
- Count nodes
- Find sum
- Search element
- Find maximum/minimum
- Check condition on every node

---

