# ⌨️ Input and Output in C

Programs are useful when they can **interact with users**.

Two common operations are:

- **Output** → Display information to the user
- **Input** → Receive data from the user

In C, these are handled using functions from the **standard input-output library**.

---

# 📚 The stdio.h Library

Before using input/output functions, we must include:

```c
#include <stdio.h>
```

This header file contains declarations for:

- `printf()`
- `scanf()`
- `getchar()`
- `putchar()`

Without this header, the compiler does not know about these functions.

---

# 🖥 Output in C: `printf()`

`printf()` is used to **display output on the screen**.

## Example

```c
#include <stdio.h>

int main()
{
    printf("Hello, World!\n");
    return 0;
}
```

## Output

```
Hello, World!
```

---

# 🧾 Format Specifiers

When printing variables, we use **format specifiers**.

| Specifier | Data Type | Example |
|----------|-----------|--------|
| `%d` | int | `printf("%d", age);` |
| `%f` | float | `printf("%f", price);` |
| `%lf` | double | `printf("%lf", value);` |
| `%c` | char | `printf("%c", grade);` |
| `%s` | string | `printf("%s", name);` |

---

# Example: Printing Variables

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

## Output

```
Age: 21
Height: 5.9
Grade: A
```

---

# 📥 Input in C: `scanf()`

`scanf()` allows the program to **receive input from the user**.

## Example

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter your age: ");
    scanf("%d", &age);

    printf("Your age is %d\n", age);

    return 0;
}
```

---

# Important Concept: Address Operator (`&`)

Notice this line:

```c
scanf("%d", &age);
```

`&age` means:

Give the **memory address of the variable `age`**.

This allows `scanf()` to store the value **directly into the variable**.

---

# Example Program: Multiple Inputs

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");

    scanf("%d %d", &a, &b);

    printf("You entered: %d and %d\n", a, b);

    return 0;
}
```

## Output Example

```
Enter two numbers: 5 8
You entered: 5 and 8
```

---

# Reading Characters

For **single characters**:

```c
char letter;

scanf("%c", &letter);
```

## Example

```c
#include <stdio.h>

int main()
{
    char grade;

    printf("Enter a grade: ");
    scanf("%c", &grade);

    printf("You entered: %c\n", grade);

    return 0;
}
```

---

# Reading Strings

Strings use `%s`.

## Example

```c
#include <stdio.h>

int main()
{
    char name[50];

    printf("Enter your name: ");
    scanf("%s", name);

    printf("Hello %s\n", name);

    return 0;
}
```

---

# ⚠️ Common Beginner Mistakes

## Forgetting `&`

Incorrect:

```c
scanf("%d", age);
```

Correct:

```c
scanf("%d", &age);
```

---

## Wrong Format Specifier

Example mistake:

```c
float price;
scanf("%d", &price);
```

Correct:

```c
scanf("%f", &price);
```

---

# 📊 Quick Summary

| Function / Specifier | Purpose |
|----------------------|--------|
| `printf()` | Display output |
| `scanf()` | Read input |
| `%d` | Integer |
| `%f` | Float |
| `%c` | Character |
| `%s` | String |

---

# 🧩 Practice Exercises

## 1️⃣ Simple Input

Write a program that:

- asks the user for their **age**
- prints it back

---

## 2️⃣ Two Number Calculator

Input two numbers and print their:

- sum
- difference
- product

---

## 3️⃣ Name Greeting Program

Ask the user for their name and print:

```
Hello <name>
```

---

# 🧠 Super Challenge

Write a program that:

- asks the user for their **name**
- asks their **age**
- asks their **height**

Then print a **formatted summary**.

Example output:

```
Name: Alex
Age: 20
Height: 5.8
```

---

# 🚀 Next Chapter

Next we will learn:

# Control Flow in C

Topics include:

- `if` statements
- `else`
- nested conditions
- decision making

This is where programs begin to **make intelligent decisions**.
