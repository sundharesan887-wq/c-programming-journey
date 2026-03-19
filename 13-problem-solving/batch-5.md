# C Programming Problem Solving Journey
## Batch 5 — Recursion Basics (Explained Simply)

This batch focuses on understanding recursion step-by-step.

---

# What is Recursion?

Recursion means:

👉 A function calls itself  

Think:

> "I will solve a smaller version of the problem again and again until it becomes easy."

---

# Important Rules

1. Must have a **stopping point (base case)**  
2. Must **reduce the problem each time**  

---

# Problem 21 — Print Numbers from 1 to N (Recursion)

## Question

Print numbers from **1 to N** using recursion.

---

## Example

```
Input:
5

Output:
1 2 3 4 5
```

---

## Simple Thinking

We want:

```
1 2 3 4 5
```

But recursion thinks like this:

```
👉 First go down to 1
👉 Then come back and print
```

---

## Code

```c
#include <stdio.h>

void printNumbers(int n)
{
    if(n == 0)
        return;

    printNumbers(n - 1);

    printf("%d ", n);
}

int main()
{
    int n;

    printf("Enter n: ");
    scanf("%d", &n);

    printNumbers(n);

    return 0;
}
```

---

## Explanation

Call:

```
printNumbers(5)
```

Execution:

```
5 → 4 → 3 → 2 → 1 → 0 (STOP)
```

Then prints while returning:

```
1 2 3 4 5
```

---

# Problem 22 — Sum of N Numbers (Recursion)

## Question

Find sum of first **N natural numbers**.

---

## Example

```
Input:
5

Output:
15
```

---

## Thinking

```
5 + 4 + 3 + 2 + 1
```

---

## Code

```c
#include <stdio.h>

int sum(int n)
{
    if(n == 0)
        return 0;

    return n + sum(n - 1);
}

int main()
{
    int n;

    printf("Enter n: ");
    scanf("%d", &n);

    printf("Sum = %d\n", sum(n));

    return 0;
}
```

---

## Explanation

```
sum(5)
= 5 + sum(4)
= 5 + 4 + sum(3)
= 5 + 4 + 3 + 2 + 1
= 15
```

---

# Problem 23 — Factorial Using Recursion

## Question

Find factorial using recursion.

---

## Example

```
Input:
5

Output:
120
```

---

## Code

```c
#include <stdio.h>

long long factorial(int n)
{
    if(n == 0 || n == 1)
        return 1;

    return n * factorial(n - 1);
}

int main()
{
    int n;

    printf("Enter n: ");
    scanf("%d", &n);

    printf("Factorial = %lld\n", factorial(n));

    return 0;
}
```

---

## Explanation

```
5! = 5 × 4 × 3 × 2 × 1 = 120
```

---

# Problem 24 — Power of a Number

## Question

Find \( x^n \) using recursion.

---

## Example

```
Input:
2 3

Output:
8
```

---

## Thinking

```
2 × 2 × 2 = 8
```

---

## Code

```c
#include <stdio.h>

int power(int x, int n)
{
    if(n == 0)
        return 1;

    return x * power(x, n - 1);
}

int main()
{
    int x, n;

    printf("Enter base and exponent: ");
    scanf("%d %d", &x, &n);

    printf("Result = %d\n", power(x, n));

    return 0;
}
```

---

## Explanation

```
power(2,3)
= 2 × power(2,2)
= 2 × 2 × power(2,1)
= 2 × 2 × 2 × 1
= 8
```

---

# Problem 25 — Fibonacci Series (Recursion)

## Question

Print nth Fibonacci number.

---

## Example

```
Input:
5

Output:
5
```

---

## Sequence

```
0 1 1 2 3 5
```

---

## Thinking

Each number is:

```
F(n) = F(n-1) + F(n-2)
```

---

## Code

```c
#include <stdio.h>

int fib(int n)
{
    if(n == 0)
        return 0;

    if(n == 1)
        return 1;

    return fib(n - 1) + fib(n - 2);
}

int main()
{
    int n;

    printf("Enter n: ");
    scanf("%d", &n);

    printf("Fibonacci = %d\n", fib(n));

    return 0;
}
```

---

## Explanation

```
fib(5)
= fib(4) + fib(3)
= (fib(3)+fib(2)) + (fib(2)+fib(1))
= 5
```

---

# Summary

Recursion works like:

```
1. Break problem into smaller problems
2. Reach base case
3. Solve backward
```

---

# ⚠ Important Note

Recursion is powerful but:

- Uses more memory (**stack**)  
- Can be slow (**especially Fibonacci**)  

# 🔁 Recursion Batch — Problems 24 & 25

This batch covers:

- Recursion basics  
- Function calling itself  
- Base case & recursive case  
- Stack behavior (down & up execution)  

---

# 🔹 Problem 24 — Power of a Number (Recursion)

## 🧾 Question

Find \( x^n \) using recursion.

---

## 📥 Example

```
Input:
2 3

Output:
8
```

---

## 🧠 Thinking

```
2^3 = 2 × 2 × 2 = 8
```

Recursive formula:

```
x^n = x × x^(n-1)
```

---

## 💻 Code

```c
#include <stdio.h>

int power(int x, int n)
{
    if(n == 0)
        return 1;

    return x * power(x, n - 1);
}

int main()
{
    int x, n;

    printf("Enter base and exponent: ");
    scanf("%d %d", &x, &n);

    printf("Result = %d\n", power(x, n));

    return 0;
}
```

---

## 🔍 Execution Flow

```
power(2,3)
= 2 × power(2,2)
= 2 × 2 × power(2,1)
= 2 × 2 × 2 × power(2,0)
= 2 × 2 × 2 × 1
= 8
```

---

## 📌 Key Concepts

- **Base Case** → `n == 0`  
- **Recursive Case** → `x * power(x, n-1)`  
- Goes **down (calls)** → then **up (returns)**  

---

# 🔹 Problem 25 — Fibonacci Series (Recursion)

## 🧾 Question

Find the nth Fibonacci number using recursion.

---

## 📥 Example

```
Input:
5

Output:
5
```

---

## 🧠 Thinking

Fibonacci sequence:

```
0 1 1 2 3 5 8 ...
```

Formula:

```
F(n) = F(n-1) + F(n-2)
```

---

## 💻 Code

```c
#include <stdio.h>

int fib(int n)
{
    if(n == 0)
        return 0;

    if(n == 1)
        return 1;

    return fib(n - 1) + fib(n - 2);
}

int main()
{
    int n;

    printf("Enter n: ");
    scanf("%d", &n);

    printf("Fibonacci = %d\n", fib(n));

    return 0;
}
```

---

## 🔍 Execution Flow

```
fib(5)
= fib(4) + fib(3)
= (fib(3)+fib(2)) + (fib(2)+fib(1))
= (2+1) + (1+1)
= 3 + 2
= 5
```

---

## 📌 Key Concepts

- **Base Cases** → `fib(0)=0`, `fib(1)=1`  
- **Recursive Case** → `fib(n-1) + fib(n-2)`  
- Repeats calculations → **inefficient**  

---

## ⚠️ Important Note

Fibonacci recursion is **slow** because it recalculates values multiple times.

---

# 🚀 Summary

| Problem | Concept |
|--------|--------|
| Power | Single recursion |
| Fibonacci | Double recursion |
| Both | Base case + recursive case |

---

# 🧠 One-Line Understanding

**Recursion breaks a big problem into smaller ones, reaches a base case, then builds the answer backward.**
