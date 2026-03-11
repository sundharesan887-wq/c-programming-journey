# 📘 C Programming — Structures, Unions, Padding & Memory Alignment

This section explains how **structures and unions store data in memory**, how **padding works**, and how to **calculate structure size**.

---

# 1️⃣ What is a Structure?

A **structure** is a user-defined data type that groups multiple variables together.

Example:

```c
struct Student
{
    int age;
    float marks;
    char grade;
};
```

This groups **related data into one unit**.

## Memory Representation

```
Student
┌──────────┬──────────┬──────────┐
│   age    │  marks   │  grade   │
└──────────┴──────────┴──────────┘
```

---

# 2️⃣ Creating a Structure Variable

```c
struct Student s1;
```

Accessing members:

```c
s1.age = 21;
s1.marks = 85.5;
s1.grade = 'A';
```

Access operator:

```
.
```

Example:

```c
printf("%d", s1.age);
```

---

# 3️⃣ Pointer to Structure

A pointer can store the **address of a structure**.

Example:

```c
struct Student *ptr;
ptr = &s1;
```

Access members using **arrow operator**:

```
ptr->age
```

Equivalent expression:

```
(*ptr).age
```

---

# 4️⃣ Structure Memory Layout

Structure members are stored **sequentially in memory**.

Example:

```c
struct A
{
    int a;
    char b;
};
```

Memory layout:

```
[a a a a][b]
```

However, this may include **padding**.

---

# 5️⃣ What is Padding?

**Padding** is extra empty memory added by the compiler to maintain proper alignment.

Example:

```
[a a a a][b x x x]
```

```
x → padding bytes
```

Padding helps the **CPU access memory faster**.

---

# 6️⃣ Memory Alignment

Each data type prefers certain **memory alignment**.

| Data Type | Size | Alignment |
|----------|------|-----------|
| char | 1 byte | any address |
| int | 4 bytes | multiple of 4 |
| float | 4 bytes | multiple of 4 |
| double | 8 bytes | multiple of 8 |

Example:

```
double must start at address multiple of 8
```

---

# 7️⃣ Structure Size Calculation Rules

### Rule 1

Each variable must start at an address **aligned to its type**.

### Rule 2

Padding is added when **alignment breaks**.

### Rule 3

The **final structure size must be a multiple of the largest member alignment**.

---

# 8️⃣ Example — Structure Size = 12

```c
struct Data
{
    int a;
    float b;
    char c;
};
```

Sizes:

```
int   → 4
float → 4
char  → 1
```

Memory:

```
[a a a a][b b b b][c x x x]
```

Total:

```
4 + 4 + 4 = 12 bytes
```

---

# 9️⃣ Tricky Example — Structure Size = 24

```c
struct A
{
    char a;
    double b;
    char c;
};
```

Step-by-step memory layout:

```
[a x x x x x x x]
[b b b b b b b b]
[c x x x x x x x]
```

Explanation:

```
char a   → 1 byte
padding  → 7 bytes
double b → 8 bytes
char c   → 1 byte
padding  → 7 bytes
```

Final size:

```
24 bytes
```

---

# 🔟 Better Memory Layout Example

```c
struct B
{
    double b;
    char a;
    char c;
};
```

Memory:

```
[b b b b b b b b][a][c][padding]
```

Size calculation:

```
8 + 1 + 1 = 10
```

Next multiple of 8:

```
16 bytes
```

Final size:

```
16 bytes
```

---

# 1️⃣1️⃣ Structure Size Calculation Trick

To estimate structure size quickly:

1. Find **largest data type size**  
2. Add sizes of **all members**  
3. Round up to **nearest multiple of largest size**  
4. Consider **alignment padding between members**

---

# 1️⃣2️⃣ Union

A **union** stores different variables in the **same memory location**.

Example:

```c
union Data
{
    int a;
    float b;
    char c;
};
```

Memory layout:

```
[a / b / c]
```

All members share the **same memory**.

Only **one value exists at a time**.

---

# 1️⃣3️⃣ Union Size Rule

Union size equals the **largest member size**.

Example:

```c
union Test
{
    int a;
    double b;
    char c;
};
```

Largest member:

```
double → 8 bytes
```

So:

```
sizeof(union Test) = 8
```

---

# 1️⃣4️⃣ Structure vs Union

| Feature | Structure | Union |
|--------|-----------|-------|
| Memory | separate memory for each member | shared memory |
| Storage | multiple values stored | one value at a time |
| Size | sum of members + padding | largest member |

---

# 1️⃣5️⃣ Example Program (Structure Size)

```c
#include <stdio.h>

struct A
{
    char a;
    double b;
    char c;
};

int main()
{
    printf("%lu", sizeof(struct A));
}
```

Output:

```
24
```

---

# 1️⃣6️⃣ Why Padding Exists

Padding is added because CPUs access **aligned memory faster**.

Without alignment:

```
CPU may need multiple memory reads
```

With alignment:

```
CPU accesses data in one operation
```

---

# 1️⃣7️⃣ Best Practice (Memory Optimization)

Always order structure members from **largest to smallest**.

### Good

```c
struct Example
{
    double b;
    int a;
    char c;
};
```

### Bad

```c
struct Example
{
    char c;
    int a;
    double b;
};
```

Ordering variables properly **reduces padding and saves memory**.

---

# ⭐ Key Rules to Remember

### Structure

```
size = sum of members + padding
```

### Union

```
size = largest member
```

### Alignment Rule

```
variables must start at addresses aligned to their size
```

### Final Structure Rule

```
structure size must be multiple of largest alignment
```

---

# 🧠 Simple Analogy

Memory is like **parking spaces**.

```
char   → bike (1 slot)
int    → car (4 slots)
double → truck (8 slots)
```

If a **truck arrives after a bike**, empty spaces are added so the truck fits properly.

Those **empty spaces are padding**.
