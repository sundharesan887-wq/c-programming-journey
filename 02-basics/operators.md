# ➗ Operators in C

Operators allow a program to **perform operations on variables and values**.

Examples of operations:

- mathematical calculations
- comparisons
- logical decisions
- updating values

Example expression:

```c
int sum = a + b;
```

Here:

- `+` → operator  
- `a` and `b` → operands  

---

# 📌 What is an Operator?

An operator is a symbol that tells the compiler to **perform an operation**.

Example:

```c
int result = 10 + 5;
```

Here:

- `10` and `5` → operands  
- `+` → operator  

Result:

```
15
```

---

# 📊 Types of Operators in C

C provides several types of operators.

| Operator Type | Purpose |
|---------------|--------|
| Arithmetic Operators | Mathematical calculations |
| Relational Operators | Compare values |
| Logical Operators | Combine conditions |
| Assignment Operators | Assign values |
| Increment / Decrement | Increase or decrease value |
| Bitwise Operators | Operate on bits |
| Conditional Operator | Ternary decision |

---

# 1️⃣ Arithmetic Operators

Used for **mathematical calculations**.

| Operator | Meaning | Example |
|--------|--------|--------|
| `+` | Addition | a + b |
| `-` | Subtraction | a - b |
| `*` | Multiplication | a * b |
| `/` | Division | a / b |
| `%` | Modulus (remainder) | a % b |

## Example Program

```c
#include <stdio.h>

int main()
{
    int a = 10;
    int b = 3;

    printf("Addition: %d\n", a + b);
    printf("Subtraction: %d\n", a - b);
    printf("Multiplication: %d\n", a * b);
    printf("Division: %d\n", a / b);
    printf("Remainder: %d\n", a % b);

    return 0;
}
```

## Output

```
Addition: 13
Subtraction: 7
Multiplication: 30
Division: 3
Remainder: 1
```

**Note:** Integer division removes decimals.

---

# 2️⃣ Relational Operators

Relational operators **compare two values**.

The result is:

- `1` → true  
- `0` → false  

| Operator | Meaning |
|--------|--------|
| `==` | Equal to |
| `!=` | Not equal |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater or equal |
| `<=` | Less or equal |

## Example

```c
#include <stdio.h>

int main()
{
    int a = 5;
    int b = 10;

    printf("%d\n", a > b);
    printf("%d\n", a < b);

    return 0;
}
```

## Output

```
0
1
```

Explanation:

```
5 > 10 → false → 0
5 < 10 → true  → 1
```

---

# 3️⃣ Logical Operators

Logical operators **combine multiple conditions**.



-`Logical AND(&&)` 

-`Logical OR(||)` 

-`Logical NOT(!)`

---

## Truth Table: Logical AND (`&&`)

| A | B | A && B |
|---|---|-------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

Meaning: **Both conditions must be true**

Example:

```c
int age = 20;

if(age > 18 && age < 30)
{
    printf("Young adult\n");
}
```

---

## Truth Table: Logical OR (`||`)

| A | B | A \|\| B |
|---|---|--------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Meaning: **At least one condition must be true**

Example:

```c
int marks = 40;

if(marks >= 50 || marks == 40)
{
    printf("Condition satisfied\n");
}
```

---

## Truth Table: Logical NOT (`!`)

| A | !A |
|---|----|
| 0 | 1 |
| 1 | 0 |

Meaning: **Reverses the condition**

Example:

```c
int isLoggedIn = 0;

if(!isLoggedIn)
{
    printf("User not logged in\n");
}
```

---

# 4️⃣ Assignment Operators

Assignment operators **store values in variables**.

Basic assignment:

```c
int x = 10;
```

Compound assignments:

| Operator | Meaning |
|--------|--------|
| `+=` | x = x + value |
| `-=` | x = x - value |
| `*=` | x = x * value |
| `/=` | x = x / value |

Example:

```c
int x = 10;

x += 5;
```

Result:

```
x = 15
```

---

# 5️⃣ Increment and Decrement

Increase or decrease a value by **1**.

| Operator | Meaning |
|--------|--------|
| `++` | Increment |
| `--` | Decrement |

Example:

```c
int x = 5;
x++;
```

Now:

```
x = 6
```

---

# Prefix vs Postfix Increment

This is a **very important concept**.

---

## Postfix Increment

Value used **first**, then increment happens.

```c
#include <stdio.h>

int main()
{
    int x = 5;

    printf("%d\n", x++);
    printf("%d\n", x);

    return 0;
}
```

### Output

```
5
6
```

Explanation:

```
Step 1 → print 5
Step 2 → increment happens
```

---

## Prefix Increment

Increment happens **first**, then value used.

```c
#include <stdio.h>

int main()
{
    int x = 5;

    printf("%d\n", ++x);
    printf("%d\n", x);

    return 0;
}
```

### Output

```
6
6
```

Explanation:

```
Step 1 → increment happens
Step 2 → print new value
```

---

# 🧩 Practice Exercises

1️⃣ Create two numbers and print their **sum**.

2️⃣ Compare two numbers using **relational operators**.

3️⃣ Use `+=` to increase a number.

4️⃣ Use **logical AND** to check two conditions.

---

# 🧠 Super Challenge (Tricky Question)

Predict the output.

```c
#include <stdio.h>

int main()
{
    int a = 5;
    int b = 10;

    int result = ++a * 2 + b-- / 2;

    printf("a = %d\n", a);
    printf("b = %d\n", b);
    printf("result = %d\n", result);

    return 0;
}
```

---

# Try Solving First

Understand:

- prefix `++`
- postfix `--`
- arithmetic operators
- operator precedence

---

# ✅ Solution Explanation

Initial values:

```
a = 5
b = 10
```

Step 1:

```
++a
```

Prefix increment:

```
a = 6
```

Step 2:

```
b-- / 2
```

Postfix decrement:

```
10 / 2 = 5
b becomes 9 afterwards
```

Step 3:

```
result = 6 * 2 + 5
```

Step 4:

```
result = 12 + 5
```

Final values:

```
result = 17
a = 6
b = 9
```

---

# Final Output

```
a = 6
b = 9
result = 17
```

---

# 🧠 Key Takeaways

You learned:

- arithmetic operators
- relational operators
- logical operators
- assignment operators
- increment & decrement
- prefix vs postfix behavior
- operator precedence basics

Operators allow programs to **calculate, compare, and make decisions**.

---

# 🚀 Next Chapter

Next we will learn:

# Input and Output in C

Where we will cover:

- `printf()`
- `scanf()`
- reading user input
- formatted input
- interactive programs
