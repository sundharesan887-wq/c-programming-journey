# 🔁 Loops in C

Programs often need to **repeat actions**.

Examples:

- Print numbers from 1 to 10
- Process items in a list
- Repeat until a condition becomes false

Loops allow programs to **execute a block of code multiple times**.

---

# 🧠 What is a Loop?

A loop is a control structure that **repeats instructions while a condition is true**.

Example idea:

```
Repeat:
print number
until number reaches 10
```

Without loops we would have to write:

```c
printf("1\n");
printf("2\n");
printf("3\n");
...
printf("10\n");
```

Loops make this **much easier and cleaner**.

---

# 📊 Types of Loops in C

C provides three types of loops.

| Loop Type | Purpose |
|----------|---------|
| `for` loop | Used when number of iterations is known |
| `while` loop | Used when condition controls repetition |
| `do-while` loop | Executes at least once |

---

# 1️⃣ The `for` Loop

The `for` loop is commonly used when we **know how many times a loop should run**.

## Syntax

```c
for(initialization; condition; update)
{
    // code to execute
}
```

---

## Example: Print Numbers 1 to 5

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

---

## Output

```
1
2
3
4
5
```

---

## Step-by-Step Execution

Initial value:

```
i = 1
```

Loop condition:

```
i <= 5
```

Execution steps:

```
1 <= 5 → print 1 → i becomes 2
2 <= 5 → print 2 → i becomes 3
3 <= 5 → print 3 → i becomes 4
4 <= 5 → print 4 → i becomes 5
5 <= 5 → print 5 → i becomes 6
6 <= 5 → false → loop stops
```

---

# 2️⃣ The `while` Loop

The `while` loop repeats **as long as a condition remains true**.

## Syntax

```c
while(condition)
{
    // code
}
```

---

## Example: Print Numbers 1 to 5

```c
#include <stdio.h>

int main()
{
    int i = 1;

    while(i <= 5)
    {
        printf("%d\n", i);
        i++;
    }

    return 0;
}
```

---

## Output

```
1
2
3
4
5
```

---

## How It Works

Initial value:

```
i = 1
```

Check condition:

```
i <= 5
```

Loop runs **while condition is true**.

Each iteration increases `i`.

---

# 3️⃣ The `do-while` Loop

The `do-while` loop **always executes at least once**.

## Syntax

```c
do
{
    // code
}
while(condition);
```

---

## Example

```c
#include <stdio.h>

int main()
{
    int i = 1;

    do
    {
        printf("%d\n", i);
        i++;
    }
    while(i <= 5);

    return 0;
}
```

---

## Output

```
1
2
3
4
5
```

---

# 🔑 Key Difference

| Loop | Condition Checked |
|-----|------------------|
| `for` | Before execution |
| `while` | Before execution |
| `do-while` | After execution |

This means **`do-while` runs at least once**.

---

# 📌 Example Showing the Difference

```c
#include <stdio.h>

int main()
{
    int x = 10;

    while(x < 5)
    {
        printf("While Loop\n");
    }

    do
    {
        printf("Do While Loop\n");
    }
    while(x < 5);

    return 0;
}
```

---

## Output

```
Do While Loop
```

---

## Explanation

```
while condition → false → never runs
do-while → runs once → then checks condition
```
# 🔁 Nested Loops in C

A **nested loop** is a loop inside another loop.

The outer loop runs first, and for **each iteration of the outer loop**, the inner loop runs completely.

## Example

```c
#include <stdio.h>

int main()
{
    int i, j;

    for(i = 1; i <= 3; i++)
    {
        for(j = 1; j <= 3; j++)
        {
            printf("* ");
        }

        printf("\n");
    }

    return 0;
}
```

---

# 🖥 Output

```
* * *
* * *
* * *
```

---

# 🧠 Understanding the Program

First let's identify the variables.

- `i` → controls **rows**
- `j` → controls **columns**

The program prints **3 rows and 3 columns of stars**.

---

# 📌 Line-by-Line Explanation

## Line 1

```c
int i, j;
```

Two variables are declared.

- `i` → outer loop counter  
- `j` → inner loop counter  

---

## Line 2 – Outer Loop

```c
for(i = 1; i <= 3; i++)
```

This loop controls **how many rows are printed**.

- Start: `i = 1`
- Condition: `i <= 3`
- Update: `i++`

So the **outer loop runs 3 times**.

---

## Line 3 – Inner Loop

```c
for(j = 1; j <= 3; j++)
```

This loop controls **how many stars appear in each row**.

- Start: `j = 1`
- Condition: `j <= 3`
- Update: `j++`

So **each row prints 3 stars**.

---

## Line 4 – Print Star

```c
printf("* ");
```

This prints a **star followed by a space**.

Important:  
There is **no newline here**, so the stars print on the **same line**.

---

## Line 5 – Move to Next Line

```c
printf("\n");
```

After the inner loop finishes printing stars, this statement moves the cursor to the **next line**.

This allows the **next row to start**.

---

# 🔄 Step-by-Step Execution

Initial values:

```
i = 1
```

---

## First Row

Outer loop runs.

```
i = 1
```

Inner loop starts.

```
j = 1 → print *
j = 2 → print *
j = 3 → print *
```

Inner loop ends.

Program prints:

```
* * *
```

Then:

```
printf("\n")
```

Moves to next line.

---

## Second Row

Outer loop continues.

```
i = 2
```

Inner loop resets.

```
j = 1 → print *
j = 2 → print *
j = 3 → print *
```

Output becomes:

```
* * *
* * *
```

---

## Third Row

Outer loop runs again.

```
i = 3
```

Inner loop runs.

```
j = 1 → print *
j = 2 → print *
j = 3 → print *
```

Final output:

```
* * *
* * *
* * *
```

---

# 🧠 Visual Loop Flow

```
Outer Loop (Rows)
   |
   |-- Inner Loop (Columns)
           |
           |-- Print "*"
```

Execution order:

```
Row 1 → print 3 stars
Row 2 → print 3 stars
Row 3 → print 3 stars
```

---

# ♾ Infinite Loops

An **infinite loop** is a loop that **never stops executing**.

This happens when the loop condition is **always true**.

## Example

```c
#include <stdio.h>

int main()
{
    while(1)
    {
        printf("This will run forever\n");
    }

    return 0;
}
```

---

# Why This Loop Never Stops

The condition is:

```
while(1)
```

Here:

```
1 → always true
```

So the loop becomes:

```
while(true)
```

Meaning the loop **never exits**.

---

# Step-by-Step Execution

1. Start program.
2. Enter `while` loop.
3. Check condition:

```
1 → true
```

4. Execute:

```c
printf("This will run forever");
```

5. Program goes back to check the condition again.

```
1 → true
```

The process repeats forever.

```
Print message
Check condition
Print message
Check condition
...
```

---

# ⚠ Another Example of Infinite Loop

```c
#include <stdio.h>

int main()
{
    int i = 1;

    while(i <= 5)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

---

# Why Is This Infinite?

Because **`i` never changes**.

Execution:

```
i = 1
1 <= 5 → true
print 1
```

Then:

```
i is still 1
1 <= 5 → true
print 1
```

This repeats **forever**.

---

# How to Fix It

We must **update the loop variable**.

Correct version:

```c
while(i <= 5)
{
    printf("%d\n", i);
    i++;
}
```

Now the loop eventually **stops**.

---

# 🧠 Key Takeaways

Nested loops allow programs to:

- create patterns
- process grids
- perform repeated structured operations

Infinite loops happen when:

- loop conditions never become false
- loop variables are not updated

Understanding loop execution **step by step** helps you **debug programs easily**.
# 🧩 Practice Exercises

## 1️⃣ Print Numbers from 1 to 10 (Using `for` Loop)

Write a program to print numbers from **1 to 10** using a `for` loop.

---

## 2️⃣ Print Numbers from 10 to 1 (Using `while` Loop)

Write a program to print numbers from **10 down to 1** using a `while` loop.

---

## 3️⃣ Multiplication Table Program

Write a program to print the **multiplication table of a number**.

### Example

```
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
...
```

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 3; i++)
    {
        printf("%d ", i);
    }

    printf("\n");

    for(i = 3; i >= 1; i--)
    {
        printf("%d ", i);
    }

    return 0;
}
```

---

# Try Before Looking

Think about how `i` changes during the loops.

---

# ✅ Solution

## First Loop

```
i = 1 → print 1
i = 2 → print 2
i = 3 → print 3
```

## Second Loop

```
i = 3 → print 3
i = 2 → print 2
i = 1 → print 1
```

---

# Final Output

```
1 2 3
3 2 1
```

---

# 🧠 Key Takeaways

You learned:

- `for` loops
- `while` loops
- `do-while` loops
- nested loops
- infinite loops

Loops allow programs to **repeat tasks efficiently**.

---

# 🚀 Next Chapter

Next we will learn:

# Functions in C

Topics include:

- function definition
- function declaration
- parameters
- return values
- modular programming
