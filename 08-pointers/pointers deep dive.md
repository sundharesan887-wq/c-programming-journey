# 📘 C Programming – Pointers (Complete Beginner Guide)

A **pointer** is a variable that stores the **memory address of another variable**.

Example:

```c
int x = 10;
int *ptr = &x;
```

Meaning:

```
x    → stores value 10
&x   → memory address of x
ptr  → stores address of x
```

---

# 🧠 Memory Example

```
Address → 1000
Value   → 10
```

```
x   = 10
&x  = 1000
ptr = 1000
```

So:

```
ptr → points to x
```

---

# 1️⃣ Pointer Declaration

## Syntax

```c
datatype *pointer_name;
```

## Example

```c
int *ptr;
```

This means:

```
ptr can store the address of an integer
```

---

# 2️⃣ Address Operator `&`

`&` is used to get the **memory address of a variable**.

Example:

```c
int x = 10;
printf("%p", &x);
```

Example Output:

```
0x7ffd8b6d6354
```

---

# 3️⃣ Dereference Operator `*`

`*` is used to **access the value stored at a memory address**.

Example:

```c
int x = 10;
int *ptr = &x;

printf("%d", *ptr);
```

Output:

```
10
```

Meaning:

```
*ptr → value stored at address ptr
```

---

# 4️⃣ `%p` Format Specifier

`%p` is used to print **memory addresses**.

Example:

```c
printf("%p", &x);
```

Example Output:

```
0x7ffd8b6d6354
```

Addresses are printed in **hexadecimal (base-16)**.

Hex digits:

```
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

Example progression:

```
6354
6358
635C
```

`C` represents **12 in hexadecimal**.

---

# 5️⃣ Pointer Arithmetic

Pointer arithmetic moves by the **size of the data type**, not by **1 byte**.

Rule:

```
ptr + n = ptr + (n × size_of_data_type)
```

Example:

```
sizeof(int) = 4 bytes
```

Memory:

```
Address → 100   104   108
Value   →  10    20    30
```

Pointer movement:

```
ptr     → 100
ptr +1  → 104
ptr +2  → 108
```

---

# 6️⃣ Traversing an Array with Pointers

Traversing means **visiting each element one by one**.

Example:

```c
#include <stdio.h>

int main()
{
    int arr[3] = {10,20,30};
    int *ptr = arr;

    for(int i=0;i<3;i++)
    {
        printf("%d\n", *(ptr+i));
    }
}
```

Output:

```
10
20
30
```

Explanation:

```
ptr+i   → move to next element
*(ptr+i) → value at that address
```

---

# 7️⃣ Alternative Traversal Method

Another common pointer traversal:

```c
for(int i=0;i<3;i++)
{
    printf("%d\n", *ptr);
    ptr++;
}
```

Here:

```
ptr++ → move pointer to next element
```

---

# 8️⃣ Arrays and Pointers Relationship

In C:

```
array name = address of first element
```

Example:

```c
int arr[3] = {10,20,30};
```

Then:

```
arr = &arr[0]
```

Proof:

```c
printf("%p\n", arr);
printf("%p\n", &arr[0]);
```

Both print the **same address**.

---

# 9️⃣ Array Access Using Pointers

These expressions are **identical**:

```
arr[i]
*(arr+i)
```

Example:

```
arr[1] = *(arr+1)
```

Both access the **same element**.

---

# 🔟 Mind-Blowing Pointer Trick

Because:

```
arr[i] = *(arr+i)
```

Addition is **commutative**:

```
*(arr+i) = *(i+arr)
```

So this also works:

```c
printf("%d", i[arr]);
```

Example:

```c
printf("%d",1[arr]);
```

Output:

```
20
```

---

# 1️⃣1️⃣ Array Decay Rule

When an array is used in an expression, it automatically becomes a **pointer to its first element**.

Example:

```c
int arr[3] = {10,20,30};

int *ptr = arr;
```

Here:

```
arr → pointer to first element
```

---

# 1️⃣2️⃣ Exceptions to Array Decay

Array **does NOT decay** in two cases.

## Case 1 — `sizeof`

```c
sizeof(arr)
```

Returns **size of entire array**.

Example:

```
3 integers × 4 bytes = 12
```

---

## Case 2 — Address Operator

```
&arr
```

Returns address of the **whole array**, not just the first element.

---

# 1️⃣3️⃣ Difference Between `arr`, `&arr`, and `&arr[0]`

Example:

```c
int arr[3];
```

| Expression | Meaning |
|------------|---------|
| `arr` | address of first element |
| `&arr[0]` | address of first element |
| `&arr` | address of entire array |

Example addresses:

```
arr      → 100
&arr[0]  → 100
&arr     → 100
```

But **pointer arithmetic differs**.

```
arr + 1 → next element
&arr +1 → next array block
```

---

# 📦 Memory Diagram

```
Address →   100   104   108
           ┌────┬────┬────┐
Value      │10  │20  │30  │
           └────┴────┴────┘
```

```
arr      = 100
arr +1   = 104
arr +2   = 108
```

---

# ⭐ 10 Must-Know Pointer Concepts

1️⃣ A pointer stores **memory addresses**.

2️⃣ `&` operator gets a variable’s **address**.

3️⃣ `*` operator accesses **value at an address**.

4️⃣ `%p` prints **memory addresses**.

5️⃣ Pointer arithmetic moves by **data type size**.

6️⃣ Arrays and pointers are **closely related**.

7️⃣ `arr[i]` and `*(arr+i)` are **identical**.

8️⃣ Array names usually **decay into pointers**.

9️⃣ Pointer traversal is **faster in some cases**.

🔟 Understanding pointers is essential for:

- arrays  
- strings  
- dynamic memory  
- data structures  

---

# 🧠 Key Pointer Rules

```
ptr  → stores address
*ptr → value at address
arr  = &arr[0]
arr[i] = *(arr+i)
```

---

# 🚀 Why Pointers Are Important

Pointers are fundamental in C because they enable:

- efficient array handling
- dynamic memory allocation
- string manipulation
- linked lists
- trees and graphs
- system programming
