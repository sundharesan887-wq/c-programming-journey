# 📦 Variables and Data Types in C

Programs often need to store information such as:

- age
- temperature
- prices
- names
- scores

To store this information, we use **variables**.

---

# 🧠 What is a Variable?

A **variable** is a named memory location used to store data.

Think of it like a **labeled box in memory**.

Example:

```
age = 20
```

Here:

- `age` → variable name  
- `20` → stored value  

## 📍 Memory Representation

When we declare a variable, the computer allocates memory.

| Variable | Value |
|---------|------|
| age | 20 |

The program can access and modify this value during execution.

---

# 🧩 Declaring a Variable

In C, every variable must be declared with a **data type**.

Example:

```c
int age;
```

This tells the compiler:

- create a variable named `age`
- it will store an **integer value**

---

# 📦 Variable Initialization

Initialization means **assigning a value when the variable is created**.

Example:

```c
int age = 20;
```

This creates the variable and assigns the value immediately.

---

# 📊 Common Data Types in C

| Data Type | Description | Example |
|----------|-------------|--------|
| `int` | Integer numbers | 10, 25 |
| `float` | Decimal numbers | 3.14, 2.5 |
| `double` | Double precision decimals | 3.14159 |
| `char` | Single character | 'A', 'z' |

---

# 🔢 Example Program

```c
#include <stdio.h>

int main()
{
    int age = 21;
    float height = 5.9;
    char grade = 'A';

    printf("Age: %d\n", age);
    printf("Height: %.1f\n", height);
    printf("Grade: %c\n", grade);

    return 0;
}
```

---

# 🧾 Code Explanation

```c
int age = 21;
```

- `int` → integer data type  
- `age` → variable name  
- `21` → value stored  

```c
float height = 5.9;
```

- `float` stores **decimal numbers**

```c
char grade = 'A';
```

- `char` stores a **single character**
- Characters must be written inside **single quotes**

---

# 🖥 Output

```
Age: 21
Height: 5.9
Grade: A
```

---

# 🎯 Format Specifiers

When printing variables using `printf`, we use **format specifiers**.

| Specifier | Data Type |
|----------|-----------|
| `%d` | integer |
| `%f` | float |
| `%lf` | double |
| `%c` | character |
| `%s` | string |

## Example

```c
printf("Age: %d", age);
```

---

# 📏 Data Type Sizes (Typical)

| Data Type | Size |
|----------|------|
| `int` | 4 bytes |
| `float` | 4 bytes |
| `double` | 8 bytes |
| `char` | 1 byte |

Actual sizes may vary depending on the system.

---

# 📛 Rules for Naming Variables

Variable names must follow certain rules.

## Allowed

```
age
student_name
totalMarks
```

## Not Allowed

```
2age
student-name
float
```

## Rules

- Cannot start with a number
- Cannot contain spaces
- Cannot use reserved keywords

---

# 📚 Reserved Keywords

Keywords are special words used by the **C language**.

Examples:

```
int
float
return
if
while
```

These **cannot be used as variable names**.

---

# 🧩 Mini Challenges

1. Create a variable to store your **age**.
2. Create a variable to store your **favorite letter**.
3. Create a variable to store your **height**.
4. Print all three values using `printf`.

Example challenge:

```c
int age = 20;
printf("Age: %d\n", age);
```

---

# 🧠 Key Takeaways

From this chapter you learned:

- What variables are
- How data is stored in memory
- Common data types in C
- Variable naming rules
- Format specifiers for printing

Variables are the **foundation of all programs**.

---

# 🚀 Next Chapter

Next we will learn:

# Operators in C

Operators allow programs to perform:

- calculations
- comparisons
- logical decisions
