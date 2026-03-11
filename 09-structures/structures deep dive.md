# 📘 C Programming – Structures (Complete Guide)

A **structure** in C is a user-defined data type that groups different variables together.

Example:

```c
struct Student
{
    int age;
    float marks;
};
```

This creates a **template for storing student information**.

---

# 1️⃣ Declaring a Structure

## Syntax

```c
struct StructureName
{
    datatype member1;
    datatype member2;
};
```

## Example

```c
struct Student
{
    int age;
    float marks;
};
```

---

# 2️⃣ Creating Structure Variables

Example:

```c
struct Student s1;
```

Memory representation:

```
s1
┌─────────────┐
│ age         │
│ marks       │
└─────────────┘
```

---

# 3️⃣ Accessing Structure Members

Use the **dot operator (`.`)**.

Example:

```c
s1.age = 21;
s1.marks = 85.5;
```

Accessing values:

```c
printf("%d", s1.age);
```

---

# 4️⃣ Structure Initialization

Example:

```c
struct Student s1 = {21, 85.5};
```

Meaning:

```
age = 21
marks = 85.5
```

---

# 5️⃣ Array of Structures

You can store **multiple structures**.

Example:

```c
struct Student s[3];
```

Memory representation:

```
s[0]
s[1]
s[2]
```

Example usage:

```c
s[0].age = 21;
s[1].age = 22;
```

---

# 6️⃣ Pointer to Structure

Pointers can store the **address of a structure**.

Example:

```c
struct Student *ptr;
```

Connecting pointer:

```c
ptr = &s1;
```

Visual:

```
ptr
 ↓
s1
```

---

# 7️⃣ Accessing Members Through Pointer

Instead of:

```
s1.age
```

We use:

```
ptr->age
```

Example:

```c
printf("%d", ptr->age);
```

---

# 8️⃣ Arrow Operator (`->`)

The arrow operator is used with **structure pointers**.

Example:

```
ptr->age
```

Meaning:

```
go to the structure ptr points to
then access age
```

Equivalent expression:

```
(*ptr).age
```

---

# 9️⃣ Structure Memory Layout

Example structure:

```c
struct Student
{
    int age;
    float marks;
};
```

Memory layout example:

```
Address 100 → age
Address 104 → marks
```

Structure variables store members **sequentially in memory**.

---

# 🔟 Nested Structures

Structures can contain **other structures**.

Example:

```c
struct Address
{
    int pincode;
};

struct Student
{
    int age;
    struct Address addr;
};
```

Access:

```
s1.addr.pincode
```

---

# 1️⃣1️⃣ Structure and Functions

Structures can be **passed to functions**.

Example:

```c
void display(struct Student s)
{
    printf("%d", s.age);
}
```

---

# 1️⃣2️⃣ Structures with Pointers (Common Pattern)

Example:

```c
struct Student s1;
struct Student *ptr = &s1;

ptr->age = 21;
```

Equivalent:

```c
(*ptr).age = 21;
```

---

# ⭐ 10 Must-Know Things About Structures

1️⃣ Structures group multiple variables into one unit.  
2️⃣ Defined using the `struct` keyword.  
3️⃣ Members are accessed using the dot operator (`.`).  
4️⃣ Structure pointers use the arrow operator (`->`).  
5️⃣ Structures can be stored in arrays.  
6️⃣ Structures can contain other structures (nested structures).  
7️⃣ Structures store members in sequential memory.  
8️⃣ Structures can be passed to functions.  
9️⃣ Structures are used to create complex data types.  
🔟 Structures are heavily used in linked lists, trees, and data structures.

---

# 🧠 Simple Real-Life Example

Think of a **student record**:

```
Student
┌─────────────┐
│ age         │
│ marks       │
│ id          │
└─────────────┘
```

This groups **related information into one structure**.

---

# 🚀 Why Structures Are Important

Structures are used to build:

- Linked Lists  
- Trees  
- Graphs  
- Databases  
- Operating systems  

Almost all **complex data structures depend on structures**.
