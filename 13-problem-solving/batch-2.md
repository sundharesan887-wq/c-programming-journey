# C Programming Problem Solving Journey
## Batch 2 — Problems 6 to 10

This batch covers:

- Decision making with `if/else`
- Logical comparisons
- Nested conditions
- Basic program design

---

# Problem 6 — Positive, Negative, or Zero

## Question

Write a C program that checks whether a number is:

- Positive
- Negative
- Zero

## Example Input/Output

```
Input:
5

Output:
Positive number
```

```
Input:
-3

Output:
Negative number
```

```
Input:
0

Output:
Number is zero
```

---

## Hint

Think of three conditions:

```
number > 0
number < 0
number == 0
```

---

## Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number > 0)
    {
        printf("Positive number\n");
    }
    else if (number < 0)
    {
        printf("Negative number\n");
    }
    else
    {
        printf("Number is zero\n");
    }

    return 0;
}
```

## Explanation

The program checks conditions in order:

1. If `number > 0` → positive  
2. If `number < 0` → negative  
3. Otherwise → zero  

---

# Problem 7 — Largest of Two Numbers

## Question

Write a C program that finds the larger of two numbers.

## Example Input/Output

```
Input:
8
5

Output:
Largest number = 8
```

---

## Hint

Use:

```c
if (a > b)
```

---

## Answer

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter first number: ");
    scanf("%d", &a);

    printf("Enter second number: ");
    scanf("%d", &b);

    if (a > b)
        printf("Largest number = %d\n", a);
    else
        printf("Largest number = %d\n", b);

    return 0;
}
```

---

## Alternative Method — Ternary Operator

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    int largest = (a > b) ? a : b;

    printf("Largest number = %d\n", largest);

    return 0;
}
```

### Explanation

The ternary operator works like:

```
(condition) ? value_if_true : value_if_false
```

---

# Problem 8 — Largest of Three Numbers

## Question

Write a program to find the largest among three numbers.

## Example Input/Output

```
Input:
3
9
5

Output:
Largest number = 9
```

---

## Hint

Think step-by-step.

First check:

```
a > b && a > c
```

Then:

```
b > a && b > c
```

Otherwise `c` is largest.

---

## Answer

```c
#include <stdio.h>

int main()
{
    int a, b, c;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a > b && a > c)
        printf("Largest number = %d\n", a);
    else if (b > a && b > c)
        printf("Largest number = %d\n", b);
    else
        printf("Largest number = %d\n", c);

    return 0;
}
```

---

## Alternative Method — Step Comparison

```c
#include <stdio.h>

int main()
{
    int a, b, c, largest;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    largest = a;

    if (b > largest)
        largest = b;

    if (c > largest)
        largest = c;

    printf("Largest number = %d\n", largest);

    return 0;
}
```

### Why this is good

This approach is often used in **algorithms**.

---

# Problem 9 — Simple Calculator

## Question

Write a C program that performs:

- Addition
- Subtraction
- Multiplication
- Division

based on the user's choice.

---

## Example Input/Output

```
Input
Number1: 10
Number2: 5
Choice: +

Output
Result = 15
```

---

## Hint

Use:

```c
if (operator == '+')
```

---

## Answer

```c
#include <stdio.h>

int main()
{
    float a, b;
    char op;

    printf("Enter first number: ");
    scanf("%f", &a);

    printf("Enter operator (+ - * /): ");
    scanf(" %c", &op);

    printf("Enter second number: ");
    scanf("%f", &b);

    if (op == '+')
        printf("Result = %.2f\n", a + b);
    else if (op == '-')
        printf("Result = %.2f\n", a - b);
    else if (op == '*')
        printf("Result = %.2f\n", a * b);
    else if (op == '/')
        printf("Result = %.2f\n", a / b);
    else
        printf("Invalid operator\n");

    return 0;
}
```

---

## Alternative — Switch Statement

```c
switch(op)
{
    case '+':
        printf("Result = %.2f\n", a + b);
        break;

    case '-':
        printf("Result = %.2f\n", a - b);
        break;

    case '*':
        printf("Result = %.2f\n", a * b);
        break;

    case '/':
        printf("Result = %.2f\n", a / b);
        break;

    default:
        printf("Invalid operator\n");
}
```

Switch is often **cleaner for multiple choices**.

---

# Problem 10 — Leap Year Checker

## Question

Write a program to check whether a year is a leap year.

---

# Leap Year Rules

A year is a leap year if:

- Divisible by **400**, OR  
- Divisible by **4 but not by 100**

---

## Example Input/Output

```
Input:
2024

Output:
Leap year
```

```
Input:
1900

Output:
Not a leap year
```

---

## Hint

Think of this logic:

```c
(year % 400 == 0) ||
(year % 4 == 0 && year % 100 != 0)
```

---

## Answer

```c
#include <stdio.h>

int main()
{
    int year;

    printf("Enter a year: ");
    scanf("%d", &year);

    if ((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0))
        printf("Leap year\n");
    else
        printf("Not a leap year\n");

    return 0;
}
```

---

## Explanation

Example: **2024**

```
2024 % 4 = 0
2024 % 100 != 0
```

So it is a **leap year**.

Example: **1900**

```
1900 % 4 = 0
1900 % 100 = 0
1900 % 400 != 0
```

So it is **not a leap year**.

---

# Summary of Batch 2

## Concepts Learned

- `if / else / else-if`
- Logical operators
- Nested conditions
- Ternary operator
- Switch statements
- Real-world conditional logic

---

# What is a Leap Year? (Simple Idea)

Normally:

```
1 year = 365 days
```

But Earth actually takes:

```
365.25 days
```

That extra **0.25 day** is saved.

After **4 years**:

```
0.25 × 4 = 1 full extra day
```

So we add **1 extra day → February has 29 days.**

Example:

```
2024 → Leap year
```

---

# Special Rule (Very Important)

A year is leap year if:

### Rule 1

Divisible by **4 → Leap year**

### Rule 2

If divisible by **100 → NOT leap year**

### Rule 3

If divisible by **400 → Leap year**

---

# Simple Decision Flow

```
divisible by 400 → Leap year
else divisible by 100 → Not leap year
else divisible by 4 → Leap year
else Not leap year
```

---

# Example 1

Input:

```
2024
```

Check:

```
2024 % 400 = not 0
2024 % 100 = not 0
2024 % 4 = 0
```

Result:

```
Leap year
```

---

# Example 2

Input:

```
1900
```

Check:

```
1900 % 400 = not 0
1900 % 100 = 0
```

Result:

```
Not leap year
```

---

# Why is 1896 Leap Year but 1900 is Not?

### Check 1896

```
1896 % 4 = 0   ✅ divisible by 4
1896 % 100 = 96 ❌ not divisible by 100
```

Result:

```
Leap Year ✅
```

---

### Check 1900

```
1900 % 4 = 0   ✅
1900 % 100 = 0 ✅
1900 % 400 = 300 ❌
```

Result:

```
Not Leap Year ❌
```

---

# Real Earth Science Reason

Earth does **NOT** take exactly **365.25 days**.

Actual value:

```
365.2422 days
```

But we approximate:

```
365.25 days
```

Error each year:

```
365.25 − 365.2422 = 0.0078 days
```

After **100 years**:

```
0.0078 × 100 = 0.78 days ≈ almost 1 extra day
```

So we remove leap years at **multiples of 100**.

Example:

```
1700 ❌
1800 ❌
1900 ❌
```

But removing too many causes the opposite problem.

So every **400 years**, we **add it back**.

Example:

```
1600 ✅
2000 ✅
2400 ✅
```

---

# Simple Table

| Year | Div by 4 | Div by 100 | Div by 400 | Result |
|-----|-----------|------------|------------|--------|
| 1896 | YES | NO | NO | Leap ✅ |
| 1900 | YES | YES | NO | Not Leap ❌ |
| 2000 | YES | YES | YES | Leap ✅ |
| 2024 | YES | NO | NO | Leap ✅ |
| 2023 | NO | NO | NO | Not Leap ❌ |

---

# Visual Memory Trick

Think of it like a **game rule**:

```
Rule 1: Every 4 → Leap
Rule 2: Every 100 → Cancel Leap
Rule 3: Every 400 → Restore Leap
```

---

# Final Logic (Plain English)

Leap year if:

```
Divisible by 4 AND NOT divisible by 100
OR
Divisible by 400
```

---

# Ultra Simple Memory Version (For Exams)

```
4 → yes
100 → no
400 → yes
```
