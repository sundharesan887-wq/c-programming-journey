# 🧩 Functions in C

As programs grow larger, writing all code inside `main()` becomes difficult to manage.

Functions help us **divide a program into smaller reusable blocks**.

This concept is called **modular programming**.

---

# 🧠 What is a Function?

A **function** is a block of code that performs a specific task.

Example tasks:

- calculate sum
- print a message
- check a condition
- process data

Instead of repeating code many times, we create a function and **call it when needed**.

---

# 📌 Basic Structure of a Function

A function consists of three main parts:

1. Function Declaration (Prototype)  
2. Function Definition  
3. Function Call  

---

# Example Program

```c
#include <stdio.h>

/* Function Declaration */
void greet();

int main()
{
    greet();   // function call

    return 0;
}

/* Function Definition */
void greet()
{
    printf("Hello! Welcome to C Programming.\n");
}
```

---

# 🖥 Output

```
Hello! Welcome to C Programming.
```

---

# 📍 Understanding Each Part

## 1️⃣ Function Declaration

```c
void greet();
```

This tells the compiler:

- A function named `greet` exists
- It takes **no parameters**
- It returns **no value**

This is also called a **function prototype**.

---

## 2️⃣ Function Definition

```c
void greet()
{
    printf("Hello! Welcome to C Programming.\n");
}
```

This contains the **actual code of the function**.

The function executes whenever it is **called**.

---

## 3️⃣ Function Call

```c
greet();
```

This statement **executes the function**.

The program jumps to the function definition and runs its code.

---

# 🔄 Execution Flow

Program execution follows this order:

```
Program starts
      ↓
Enter main()
      ↓
Call greet()
      ↓
Execute greet() function
      ↓
Return to main()
      ↓
Program ends
```

---

# 📦 Functions with Parameters

Functions can receive **input values called parameters**.

## Example

```c
#include <stdio.h>

void add(int a, int b)
{
    int sum = a + b;
    printf("Sum = %d\n", sum);
}

int main()
{
    add(5, 3);

    return 0;
}
```

---

# Output

```
Sum = 8
```

---

# How It Works

Function call:

```
add(5, 3)
```

Values passed:

```
a = 5
b = 3
```

Function calculates:

```
sum = a + b
sum = 8
```

---

# 📥 Functions with Return Values

Some functions **return a result to the caller**.

## Example

```c
#include <stdio.h>

int add(int a, int b)
{
    int sum = a + b;
    return sum;
}

int main()
{
    int result;

    result = add(4, 6);

    printf("Sum = %d\n", result);

    return 0;
}
```

---

# Output

```
Sum = 10
```

---

# Step-by-Step Execution

Initial call:

```
add(4, 6)
```

Inside function:

```
a = 4
b = 6
sum = 10
```

Return:

```
return 10
```

Back in `main()`:

```
result = 10
```

---

# 📊 Types of Functions in C

Functions can be categorized based on **parameters and return values**.

| Type | Description |
|-----|-------------|
| No parameters, no return value | Simple function |
| Parameters, no return value | Takes input but prints result |
| Parameters with return value | Returns result |
| No parameters with return value | Computes internally |

---

# Example of All Types

## No Parameters, No Return

```c
void greet()
{
    printf("Hello!\n");
}
```

---

## Parameters, No Return

```c
void printSum(int a, int b)
{
    printf("%d\n", a + b);
}
```

---

## Parameters with Return Value

```c
int multiply(int x, int y)
{
    return x * y;
}
```

---

# 🎯 Why Functions Are Important

Functions provide several benefits:

- Code reusability
- Better organization
- Easier debugging
- Reduced repetition

Example:

Instead of writing the **same calculation multiple times**, we create a **function**.

---

# 🧩 Practice Exercises

## 1️⃣ Greeting Function

Create a function that prints:

```
Welcome to C Programming
```

---

## 2️⃣ Square Function

Create a function that **returns the square of a number**.

Example:

```
Input: 5
Output: 25
```

---

## 3️⃣ Largest Number

Write a function that **returns the largest of two numbers**.

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

int multiply(int a, int b)
{
    return a * b;
}

int main()
{
    int x = 3;
    int y = 4;

    int result = multiply(x + 1, y + 2);

    printf("%d\n", result);

    return 0;
}
```

---

# Try Before Looking

Think about how the **parameters are passed**.

---

# ✅ Solution

Function call:

```
multiply(x + 1, y + 2)
```

Substitute values:

```
x = 3
y = 4
```

So:

```
multiply(4, 6)
```

Inside function:

```
4 * 6 = 24
```

---

# Final Output

```
24
```

---

# 🧠 Key Takeaways

You learned:

- function declaration
- function definition
- function calls
- parameters
- return values
- modular programming

Functions make programs **cleaner, reusable, and easier to maintain**.

---

# 🚀 Next Chapter

Next we will explore:

# Arrays in C

Topics include:

- array declaration
- accessing elements
- loops with arrays
- common array operations
