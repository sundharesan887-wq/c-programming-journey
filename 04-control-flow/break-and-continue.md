# ⛔ break and continue in C

Loops repeat code multiple times, but sometimes we want to **change the normal loop behavior**.

Two important statements help control loops:

- `break`
- `continue`

These are called **loop control statements**.

---

# 📌 The `break` Statement

The `break` statement **immediately stops a loop**.

When `break` executes:

1. The loop stops instantly.
2. Program control moves to the first statement **after the loop**.

---

# Syntax

```c
break;
```

---

# Example 1 — Using `break` in a Loop

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 10; i++)
    {
        if(i == 5)
        {
            break;
        }

        printf("%d\n", i);
    }

    return 0;
}
```

---

# Output

```
1
2
3
4
```

---

# Step-by-Step Execution

Initial value:

```
i = 1
```

Execution flow:

```
i = 1 → print 1
i = 2 → print 2
i = 3 → print 3
i = 4 → print 4
i = 5 → break executes
```

Loop stops immediately.

Program exits the loop.

---

# Visual Flow

```
Loop Start
   ↓
Check condition
   ↓
Check break condition
   ↓
If true → exit loop
```

---

# Real-Life Analogy

Imagine searching for a book on a shelf.

```
Check book 1
Check book 2
Check book 3
Found the book → stop searching
```

This **"stop searching"** behavior is like `break`.

---

# 📌 The `continue` Statement

The `continue` statement **skips the current iteration of a loop**.

Instead of stopping the loop, it **jumps to the next iteration**.

---

# Syntax

```c
continue;
```

---

# Example 2 — Using `continue`

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        if(i == 3)
        {
            continue;
        }

        printf("%d\n", i);
    }

    return 0;
}
```

---

# Output

```
1
2
4
5
```

---

# Step-by-Step Execution

Initial value:

```
i = 1
```

Execution flow:

```
i = 1 → print 1
i = 2 → print 2
i = 3 → continue → skip printing
i = 4 → print 4
i = 5 → print 5
```

The loop **continues even after `continue`**.

---

# Visual Flow

```
Loop Start
   ↓
Check condition
   ↓
Check continue condition
   ↓
If true → skip remaining code
   ↓
Next iteration
```

---

# Difference Between `break` and `continue`

| Statement | Effect |
|----------|--------|
| `break` | Stops the loop completely |
| `continue` | Skips current iteration |

---

# Example Comparing Both

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        if(i == 3)
        {
            continue;
        }

        if(i == 5)
        {
            break;
        }

        printf("%d\n", i);
    }

    return 0;
}
```

---

# Output

```
1
2
4
```

---

# Execution Logic

```
i = 1 → print 1
i = 2 → print 2
i = 3 → continue → skip
i = 4 → print 4
i = 5 → break → stop loop
```

---

# ⚠ Common Beginner Mistake

Placing code **after `continue`** that you expect to run.

Example mistake:

```c
if(i == 3)
{
    continue;
}

printf("Hello");
```

When `continue` runs, `"Hello"` is **skipped**.

---

# 🧩 Practice Exercises

## 1️⃣ Stop Loop Early

Write a program that prints numbers **1–10** but **stops when it reaches 7**.

---

## 2️⃣ Skip Even Numbers

Print numbers **1–10**, but skip all **even numbers**.

Hint:

```c
if(number % 2 == 0)
```

---

## 3️⃣ Multiples of 3

Print numbers from **1–20**, skipping **multiples of 3**.

---

# 🧠 Super Challenge

Predict the output:

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 10; i++)
    {
        if(i % 2 == 0)
            continue;

        if(i > 7)
            break;

        printf("%d ", i);
    }

    return 0;
}
```

---

# Try Before Looking

Follow the loop carefully.

---

# ✅ Solution

Loop execution:

```
i = 1 → print 1
i = 2 → even → continue
i = 3 → print 3
i = 4 → even → continue
i = 5 → print 5
i = 6 → even → continue
i = 7 → print 7
i = 8 → break condition triggered
```

---

# Final Output

```
1 3 5 7
```

---

# 🧠 Key Takeaways

You learned:

- `break` stops loops
- `continue` skips iterations
- how to control loop execution
- how loops behave step-by-step

These statements are **essential when writing efficient programs**.

---

# 🚀 Next Chapter

Next we will learn:

# Functions in C

Topics include:

- function declaration
- function definition
- parameters
- return values
- modular programming
