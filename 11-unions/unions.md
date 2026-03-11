# 🔗 Unions in C

In C programming, **structures and unions** are used to group multiple variables into a single unit.

However, they behave differently in memory.

Understanding this difference is very important.

---

# 🧠 What is a Union?

A **union** is a user-defined data type similar to a structure.

But unlike structures, **all members share the same memory location**.

This means:

```
Only one member of the union can store a value at a time
```

---

# Structure vs Union

| Feature | Structure | Union |
|------|------|------|
| Memory allocation | Separate memory for each member | Shared memory |
| Size | Sum of all members | Size of largest member |
| Simultaneous values | All members can store values | Only one member valid at a time |
| Usage | Storing related data | Memory optimization |

---

# 📦 Example Structure

```c
struct Data
{
    int i;
    float f;
    char c;
};
```

Memory layout:

```
| int | float | char |
```

Total memory = **sum of all members**.

---

# 📦 Example Union

```c
union Data
{
    int i;
    float f;
    char c;
};
```

Memory layout:

```
| shared memory |
```

All members use the **same memory space**.

---

# 📊 Memory Representation

Example union:

```c
union Data
{
    int i;
    float f;
    char c;
};
```

Memory:

| Address | Content |
|--------|--------|
| 1000 | union data |

All variables refer to the **same memory location**.

---

# 📌 Declaring a Union

## Syntax

```c
union UnionName
{
    datatype member1;
    datatype member2;
};
```

## Example

```c
union Data
{
    int i;
    float f;
    char c;
};
```

---

# Creating Union Variables

Example:

```c
union Data data1;
```

Access members using:

```
.
```

Example:

```
data1.i
data1.f
data1.c
```

---

# Example Program

```c
#include <stdio.h>

union Data
{
    int i;
    float f;
    char c;
};

int main()
{
    union Data data;

    data.i = 10;
    printf("Integer: %d\n", data.i);

    data.f = 5.5;
    printf("Float: %.2f\n", data.f);

    data.c = 'A';
    printf("Character: %c\n", data.c);

    return 0;
}
```

---

# Important Behavior

Each new assignment **overwrites the previous value**.

Example flow:

```
data.i = 10
```

Memory now stores:

```
10
```

Next:

```
data.f = 5.5
```

Memory now stores:

```
5.5
```

The previous integer value is **lost**.

---

# ⚠ Demonstration Program

```c
#include <stdio.h>

union Data
{
    int i;
    float f;
};

int main()
{
    union Data d;

    d.i = 10;
    printf("i = %d\n", d.i);

    d.f = 3.14;
    printf("f = %f\n", d.f);

    printf("i after storing float = %d\n", d.i);

    return 0;
}
```

Example Output:

```
i = 10
f = 3.140000
i after storing float = 1078523331
```

Explanation:

The **float overwrites the memory used by the integer**.

---

# 📊 Size of Union

Example:

```c
union Data
{
    int i;
    float f;
    char c;
};
```

Typical sizes:

```
int   = 4 bytes
float = 4 bytes
char  = 1 byte
```

Union size = **largest member**

```
4 bytes
```

---

# Example Program

```c
#include <stdio.h>

union Data
{
    int i;
    float f;
    char c;
};

int main()
{
    printf("%lu\n", sizeof(union Data));

    return 0;
}
```

Output:

```
4
```

---

# 📌 Union with Structures

Unions are often used inside structures.

Example:

```c
struct Value
{
    int type;

    union
    {
        int i;
        float f;
    } data;
};
```

This technique is used in **compilers and interpreters**.

---

# ⚠ Common Beginner Mistakes

## Expecting all values to exist simultaneously

Wrong assumption:

```
union stores multiple values
```

Reality:

```
only the last assigned value remains valid
```

---

## Using unions when structures are required

Use unions only when **memory optimization is necessary**.

---

# 🧩 Practice Exercises

## 1️⃣ Union Declaration

Create a union containing:

- int  
- float  
- char  

Print the **size of the union**.

---

## 2️⃣ Value Overwrite

Assign an integer and then a float to the same union and print results.

Observe how **memory changes**.

---

## 3️⃣ Union Memory Test

Store different values in union members and observe behavior.

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

union Test
{
    int x;
    char c;
};

int main()
{
    union Test t;

    t.x = 65;

    printf("%c\n", t.c);

    return 0;
}
```

---

# Try Before Looking

Think about how memory is shared.

---

# ✅ Solution

Value stored:

```
x = 65
```

ASCII value:

```
65 → 'A'
```

Since the same memory is accessed as a character:

```
c = 'A'
```

---

# Final Output

```
A
```

---

# 🧠 Key Takeaways

You learned:

- what unions are
- difference between structures and unions
- shared memory concept
- union size behavior
- union usage scenarios

Unions are mainly used for **memory-efficient data representation**.

---

# 🚀 Next Chapter

Next we will learn:

# Dynamic Memory Allocation

Topics include:

- `malloc()`
- `calloc()`
- `realloc()`
- `free()`

This allows programs to **allocate memory during runtime**.
