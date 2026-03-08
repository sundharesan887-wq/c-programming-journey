# 🧩 Structure of a C Program

Before writing larger programs, it is important to understand the **standard structure of a C program**.

Most well-organized C programs follow a common structure:

```c
/* Documentation Section */

#include <stdio.h>

/* Global Declarations */
int global_variable = 10;

/* Function Prototype */
void greet();

/* Main Function */
int main()
{
    greet();
    printf("Program executed successfully\n");
    return 0;
}

/* User Defined Function */
void greet()
{
    printf("Hello, welcome to C Programming Journey!\n");
}
```

Understanding each section will help you write **clean, maintainable, and professional programs**.

---

# 📌 Basic Structure Overview

A typical C program contains the following sections:

1. Documentation Section  
2. Preprocessor / Link Section  
3. Global Declaration Section  
4. Function Prototype Section  
5. `main()` Function  
6. Local Declarations  
7. Program Statements  
8. User Defined Functions  

---

# 1️⃣ Documentation Section

```c
/* Documentation Section */
```

## Purpose

The documentation section contains **comments describing the program**.

Comments are used to explain:

- What the program does
- Who wrote it
- When it was written
- Important notes about the code

## Example

```c
/*
Program: Simple Greeting Program
Author: Sundharesan
Description: Demonstrates the structure of a C program
*/
```

## Types of Comments

| Type | Example |
|-----|-----|
| Single line | `// This is a comment` |
| Multi line | `/* This is a multi-line comment */` |

## Why It Matters

Good documentation helps:

- Other programmers understand your code
- Future you understand your code

---

# 2️⃣ Link Section (Header Files)

```c
#include <stdio.h>
```

## Purpose

This section **links header files needed for the program**.

Header files contain **function declarations and macros**.

## Example Header Files

| Header File | Purpose |
|-------------|--------|
| `stdio.h` | Input and output functions |
| `math.h` | Mathematical functions |
| `string.h` | String handling functions |
| `stdlib.h` | Memory allocation and utilities |

## Example

```c
#include <stdio.h>
#include <math.h>
```

## Why It Matters

Without linking header files, the compiler **will not recognize library functions**.

Example:

`printf()` requires `stdio.h`.

---

# 3️⃣ Global Declaration Section

Global variables are declared **outside all functions**.

```c
int global_variable = 10;
```

## Purpose

Global variables can be **accessed by all functions in the program**.

## Example

```c
int counter = 0;
float pi = 3.14;
```

## When to Use Global Variables

Use them when **data must be shared across multiple functions**.

## When to Avoid Them

Too many global variables can make programs **harder to maintain**.

---

# 4️⃣ Function Prototype Section

Function prototypes **declare functions before they are used**.

```c
void greet();
```

## Purpose

They inform the compiler about:

- Function name
- Return type
- Parameters

## Example

```c
int add(int a, int b);
```

This means:

- Function name → `add`
- Returns → `integer`
- Takes → **two integers as parameters**

## Why Prototypes Matter

They allow functions to be **defined later in the program**.

---

# 5️⃣ The `main()` Function

```c
int main()
{
}
```

## Purpose

`main()` is the **entry point of every C program**.

When a program runs:

1. The operating system loads the program  
2. Execution begins inside `main()`

## Syntax

```c
int main()
{
    // program code
    return 0;
}
```

## Why `int`?

`main()` returns an **integer value to the operating system**.

`return 0;` means the program **finished successfully**.

---

# 6️⃣ Local Declarations

Variables declared **inside a function** are called **local variables**.

## Example

```c
int main()
{
    int age = 20;
}
```

## Characteristics

- Accessible only **inside the function**
- Destroyed when the function **finishes execution**

## Example

```c
int main()
{
    int number = 10;
    float price = 5.99;
}
```

---

# 7️⃣ Program Statements

Statements are **instructions executed by the computer**.

## Example

```c
printf("Hello World\n");
```

Statements perform actions such as:

- Printing output
- Taking input
- Performing calculations
- Calling functions

## Important Rule

Every statement must end with a **semicolon (`;`)**.

## Example

```c
printf("Hello\n");
```

Without the semicolon the compiler **produces an error**.

---

# 8️⃣ User Defined Functions

Programs often contain **additional functions**.

## Example

```c
void greet()
{
    printf("Hello from function!\n");
}
```

## Why Functions Are Useful

Functions help:

- Organize code
- Reuse logic
- Make programs easier to understand

## Example

```c
void greet()
{
    printf("Welcome!\n");
}
```

And called inside `main()`:

```c
greet();
```

---

# 🔁 Program Execution Flow

The execution flow of a program looks like this:

```
Program starts
      ↓
main() function begins
      ↓
Statements execute
      ↓
Functions are called
      ↓
return 0;
      ↓
Program ends
```

---

# 📦 Complete Example Program

```c
/*
Program demonstrating structure of C program
*/

#include <stdio.h>

/* Global declaration */
int global_number = 5;

/* Function prototype */
void greet();

int main()
{
    printf("Global number = %d\n", global_number);

    greet();

    return 0;
}

void greet()
{
    printf("Hello from greet function!\n");
}
```

---

# 🧠 Key Takeaways

From this chapter you learned:

- Structure of a C program
- Documentation section
- Header files
- Global variables
- Function prototypes
- `main()` function
- Local variables
- Program statements
- User defined functions

Understanding this structure helps you write **organized and scalable programs**.

---

✅ Output of the Program

When this C program is compiled and executed, the output will be:

Global number = 5

Hello from greet function!

---

# 🧩 Mini Challenges

1. Add another **global variable** to the program.
2. Create a **new function that prints your name**.
3. Call that function from `main()`.
4. Modify the program to **print two messages**.

---

# 🚀 Next Chapter

Next we will explore:

## Variables and Data Types in C

This is where programs begin **storing and manipulating real data**.
