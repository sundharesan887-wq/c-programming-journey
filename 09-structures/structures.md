# 🧱 Structures in C

In many programs we need to store **different types of information together**.

Example: **Student information**

- name  
- age  
- marks  

Without structures we would need separate variables:

```c
char name[20];
int age;
float marks;
```

This becomes difficult when managing many students.

**Structures solve this problem.**

---

# 🧠 What is a Structure?

A **structure** is a user-defined data type that groups different data types into a single unit.

Example:

```c
struct Student
{
    char name[20];
    int age;
    float marks;
};
```

Here:

```
Student → structure name
name, age, marks → members
```

---

# 📦 Declaring Structure Variables

After defining a structure, we can create variables of that type.

Example:

```c
struct Student s1;
```

This creates a variable `s1` containing:

```
s1.name
s1.age
s1.marks
```

---

# 📌 Example Program

```c
#include <stdio.h>

struct Student
{
    char name[20];
    int age;
    float marks;
};

int main()
{
    struct Student s1;

    printf("Enter name: ");
    scanf("%s", s1.name);

    printf("Enter age: ");
    scanf("%d", &s1.age);

    printf("Enter marks: ");
    scanf("%f", &s1.marks);

    printf("\nStudent Details\n");
    printf("Name: %s\n", s1.name);
    printf("Age: %d\n", s1.age);
    printf("Marks: %.2f\n", s1.marks);

    return 0;
}
```

---

# Accessing Structure Members

Structure members are accessed using the **dot operator (`.`)**.

Example:

```
s1.age
s1.marks
s1.name
```

---

# 📊 Memory Representation

Example structure:

```c
struct Student
{
    char name[20];
    int age;
    float marks;
};
```

Memory layout:

```
| name | age | marks |
```

Each member has its **own memory space**.

---

# 🔁 Array of Structures

We can store multiple structures using arrays.

Example:

```c
struct Student students[3];
```

This creates storage for **3 students**.

---

## Example Program

```c
#include <stdio.h>

struct Student
{
    char name[20];
    int age;
};

int main()
{
    struct Student students[2];

    for(int i = 0; i < 2; i++)
    {
        printf("Enter name: ");
        scanf("%s", students[i].name);

        printf("Enter age: ");
        scanf("%d", &students[i].age);
    }

    printf("\nStudent Records:\n");

    for(int i = 0; i < 2; i++)
    {
        printf("%s %d\n", students[i].name, students[i].age);
    }

    return 0;
}
```

---

# 🔗 Pointer to Structure

Pointers can also reference structures.

Example:

```c
struct Student *ptr;
```

---

## Example Program

```c
#include <stdio.h>

struct Student
{
    int age;
};

int main()
{
    struct Student s1;
    struct Student *ptr;

    ptr = &s1;

    s1.age = 21;

    printf("%d\n", ptr->age);

    return 0;
}
```

---

# The Arrow Operator (`->`)

When using **pointers to structures**, we use:

```
->
```

instead of:

```
.
```

Example:

```
ptr->age
```

Equivalent to:

```
(*ptr).age
```

---

# ⚠ Common Beginner Mistakes

## Forgetting `struct`

Wrong:

```c
Student s1;
```

Correct:

```c
struct Student s1;
```

(unless using `typedef`, which we will learn later)

---

## Incorrect Member Access

Wrong:

```c
s1->age
```

Correct:

```c
s1.age
```

---

# 🧩 Practice Exercises

## 1️⃣ Student Structure

Create a structure containing:

- name  
- roll number  
- marks  

Print the values.

---

## 2️⃣ Product Structure

Create a structure storing:

- product name  
- price  
- quantity  

Calculate **total price**.

---

## 3️⃣ Array of Structures

Store data of **3 students** and display them.

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

struct Data
{
    int x;
    int y;
};

int main()
{
    struct Data d = {5,10};

    struct Data *ptr = &d;

    ptr->x = ptr->x + ptr->y;

    printf("%d\n", d.x);

    return 0;
}
```

---

# Try Before Looking

Follow the pointer operations carefully.

---

# ✅ Solution

Initial values:

```
x = 5
y = 10
```

Operation:

```
ptr->x = ptr->x + ptr->y
```

Calculation:

```
5 + 10 = 15
```

Now:

```
d.x = 15
```

---

# Final Output

```
15
```

---

# 🧠 Key Takeaways

You learned:

- structure declaration  
- structure variables  
- member access  
- arrays of structures  
- pointers to structures  

Structures allow programs to **represent complex real-world data**.

---

# 🚀 Next Chapter

Next we will explore:

# File Handling in C

Topics include:

- reading files  
- writing files  
- file pointers  
- file operations  

File handling allows programs to **store data permanently**.
