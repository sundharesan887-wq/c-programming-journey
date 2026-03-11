# 👉 Pointers in C

Pointers are one of the most powerful features of the **C language**.

They allow programs to **directly access and manipulate memory addresses**.

Pointers are used in:

- dynamic memory allocation
- arrays and strings
- data structures
- system programming

---

# 🧠 Understanding Memory

Every variable in a program is stored in **memory**.

Example:

```c
int age = 20;
```

The computer stores this value in a memory location.

Example representation:

| Address | Value |
|--------|------|
| 1000 | 20 |

Here:

```
age = 20
memory address = 1000
```

---

# 📌 Address Operator (`&`)

To get the **memory address of a variable**, we use:

```
&
```

Example:

```c
#include <stdio.h>

int main()
{
    int age = 20;

    printf("%p\n", &age);

    return 0;
}
```

Example Output:

```
0x7ffe8b2a
```

This is the **memory address of `age`**.

---

# 📌 What is a Pointer?

A **pointer** is a variable that stores the **memory address of another variable**.

Example:

```c
int *ptr;
```

Meaning:

```
ptr → pointer variable
*   → indicates pointer
int → pointer stores address of an integer
```

---

# 📌 Declaring a Pointer

## Syntax

```c
datatype *pointer_name;
```

## Example

```c
int *ptr;
```

---

# 📌 Assigning Address to a Pointer

Example:

```c
int age = 20;
int *ptr;

ptr = &age;
```

Now:

```
ptr stores the address of age
```

Memory view:

| Variable | Address | Value |
|---------|--------|------|
| age | 1000 | 20 |
| ptr | 2000 | 1000 |

---

# 📌 Dereferencing a Pointer

Dereferencing means **accessing the value stored at the address**.

Operator used:

```
*
```

Example:

```c
#include <stdio.h>

int main()
{
    int age = 20;
    int *ptr;

    ptr = &age;

    printf("%d\n", *ptr);

    return 0;
}
```

Output:

```
20
```

Explanation:

```
ptr → address of age
*ptr → value stored at that address
```

---

# 📦 Complete Pointer Example

```c
#include <stdio.h>

int main()
{
    int num = 10;
    int *ptr;

    ptr = &num;

    printf("Value of num: %d\n", num);
    printf("Address of num: %p\n", &num);
    printf("Pointer value: %p\n", ptr);
    printf("Value using pointer: %d\n", *ptr);

    return 0;
}
```

## Example Output

```
Value of num: 10
Address of num: 0x7ffdf1
Pointer value: 0x7ffdf1
Value using pointer: 10
```

Notice:

```
ptr and &num have the same address
```

---

# 🔄 Changing Value Using Pointer

Pointers can **modify variables**.

Example:

```c
#include <stdio.h>

int main()
{
    int num = 10;
    int *ptr = &num;

    *ptr = 50;

    printf("%d\n", num);

    return 0;
}
```

Output:

```
50
```

Explanation:

```
*ptr = 50
```

changes the value stored in `num`.

---

# 📊 Pointer and Array Relationship

Arrays and pointers are **closely related**.

Example:

```c
int arr[3] = {10,20,30};
```

Memory layout:

| Index | Address | Value |
|------|--------|------|
| 0 | 1000 | 10 |
| 1 | 1004 | 20 |
| 2 | 1008 | 30 |

Array name acts like a **pointer**.

Example:

```c
printf("%d\n", *arr);
```

Output:

```
10
```

---

# Pointer Traversing an Array

Example:

```c
#include <stdio.h>

int main()
{
    int arr[3] = {10,20,30};
    int *ptr = arr;

    for(int i = 0; i < 3; i++)
    {
        printf("%d\n", *(ptr + i));
    }

    return 0;
}
```

## Output

```
10
20
30
```

Explanation:

```
ptr + i moves through array addresses
```

---

# ⚠ Common Beginner Mistakes

## Using Uninitialized Pointer

Wrong:

```c
int *ptr;
*ptr = 10;
```

This causes **undefined behavior**.

---

## Forgetting Address Operator

Wrong:

```c
ptr = num;
```

Correct:

```c
ptr = &num;
```

---

# 📚 Pointer Terminology

| Term | Meaning |
|-----|--------|
| Pointer | variable storing address |
| Address | memory location |
| Dereferencing | accessing value at address |
| Null pointer | pointer with no valid address |

Example:

```c
int *ptr = NULL;
```

---

# 🧩 Practice Exercises

## 1️⃣ Print Address

Create a variable and print its **memory address**.

---

## 2️⃣ Pointer Value

Store a variable's address in a pointer and **print the value using the pointer**.

---

## 3️⃣ Modify Value

Use a pointer to **change a variable's value**.

Example:

```
Initial value = 10
After pointer change = 50
```

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

int main()
{
    int x = 5;
    int *p = &x;

    *p = *p + 10;

    printf("%d\n", x);

    return 0;
}
```

---

# Try Before Looking

Track how the value changes.

---

# ✅ Solution

Initial:

```
x = 5
p = address of x
```

Operation:

```
*p = *p + 10
```

Meaning:

```
5 + 10 = 15
```

Now:

```
x = 15
```

---

# Final Output

```
15
```

---

# 🧠 Key Takeaways

You learned:

- memory addresses
- pointer declaration
- address operator `&`
- dereference operator `*`
- modifying variables using pointers
- pointers with arrays

Pointers allow C programs to **directly manipulate memory**.

---

# 🚀 Next Chapter

Next we will learn:

# Structures in C

Topics include:

- `struct` declaration
- struct variables
- accessing struct members
- arrays of structures
