# 🔀 Control Flow in C – if, else, else if

Programs often need to make **decisions**.

Example situations:

- If age ≥ 18 → allow voting
- If marks ≥ 50 → pass
- If password is correct → login

In C, we control decision making using **if statements**.

---

# 🧠 What is Control Flow?

Control flow determines **which part of a program runs** depending on conditions.

Example logic:

```
If condition is true → execute code
Otherwise → skip it
```

---

# 1️⃣ The `if` Statement

The `if` statement executes code **only when a condition is true**.

## Syntax

```c
if(condition)
{
    // code to execute
}
```

## Example

```c
#include <stdio.h>

int main()
{
    int age = 20;

    if(age >= 18)
    {
        printf("You are eligible to vote\n");
    }

    return 0;
}
```

## Output

```
You are eligible to vote
```

## How it Works

```
age = 20
condition → age >= 18
20 >= 18 → true
Execute the code inside if block
```

---

# 2️⃣ The `if-else` Statement

Sometimes we want **two possible outcomes**.

Example:

- pass / fail
- even / odd
- login success / failure

## Syntax

```c
if(condition)
{
    // code if true
}
else
{
    // code if false
}
```

## Example Program

```c
#include <stdio.h>

int main()
{
    int marks = 40;

    if(marks >= 50)
    {
        printf("Pass\n");
    }
    else
    {
        printf("Fail\n");
    }

    return 0;
}
```

## Output

```
Fail
```

---

# 3️⃣ The `else if` Ladder

When we have **multiple conditions**, we use `else if`.

Example: **grading system**.

## Syntax

```c
if(condition1)
{
}
else if(condition2)
{
}
else
{
}
```

## Example Program

```c
#include <stdio.h>

int main()
{
    int marks = 75;

    if(marks >= 90)
    {
        printf("Grade A\n");
    }
    else if(marks >= 70)
    {
        printf("Grade B\n");
    }
    else if(marks >= 50)
    {
        printf("Grade C\n");
    }
    else
    {
        printf("Fail\n");
    }

    return 0;
}
```

## Output

```
Grade B
```

## Execution Flow

```
marks = 75
check marks ≥ 90 → false
check marks ≥ 70 → true
print Grade B
```

---

# 4️⃣ Nested `if` Statements

An `if` inside another `if` is called a **nested if**.

# 🗳 Nested Decision Making – Age and Nationality Example

Let’s understand a real-world scenario:

To vote in a country, a person must:

1. Be at least **18 years old**
2. Be a **citizen of that country**

This means:

- Condition 1 must be **true**
- Condition 2 must also be **true**

This is a perfect example for **nested `if` statements**.

---

# 📄 The Program

```c
#include <stdio.h>

int main()
{
    int age = 20;
    int citizen = 1;  // 1 means citizen, 0 means not a citizen

    if(age >= 18)
    {
        if(citizen == 1)
        {
            printf("Eligible to vote\n");
        }
        else
        {
            printf("Not eligible: Not a citizen\n");
        }
    }
    else
    {
        printf("Not eligible: Too young\n");
    }

    return 0;
}
```

---

# 🧠 Step-by-Step Execution (Like the Computer Thinks)

Initial values:

```
age = 20
citizen = 1
```

---

## Step 1: Check First Condition

```c
if(age >= 18)
```

Evaluate:

```
20 >= 18 → true
```

Since it is **true**, the program enters this block:

```c
{
    if(citizen == 1)
    {
        printf("Eligible to vote\n");
    }
    else
    {
        printf("Not eligible: Not a citizen\n");
    }
}
```

---

## Step 2: Check Nested Condition

Now the program evaluates:

```c
if(citizen == 1)
```

Evaluate:

```
1 == 1 → true
```

So this line executes:

```c
printf("Eligible to vote\n");
```

---

# ✅ Final Output

```
Eligible to vote
```

---

# 🔍 What If Values Change?

Let’s test different scenarios.

---

## Case 1: Too Young

```
age = 16
citizen = 1
```

Step 1:

```
16 >= 18 → false
```

So the program **skips the nested block completely** and executes:

```c
printf("Not eligible: Too young\n");
```

### Output

```
Not eligible: Too young
```

---

## Case 2: Old Enough but Not Citizen

```
age = 25
citizen = 0
```

Step 1:

```
25 >= 18 → true
```

Step 2:

```
0 == 1 → false
```

So this executes:

```c
printf("Not eligible: Not a citizen\n");
```

### Output

```
Not eligible: Not a citizen
```

---

# 🧩 Why Nested `if` is Used Here

We use nested `if` because:

The **second condition (citizen check)** only matters

If the **first condition (age check)** is true.

Logical flow:

```
Check Age
    ↓
If true → Check Citizenship
    ↓
If true → Eligible
If false → Not Citizen
If age false → Too Young
```

---

# 🔄 Alternative Using Logical AND

We can also write this using a **logical operator**.

```c
#include <stdio.h>

int main()
{
    int age = 20;
    int citizen = 1;

    if(age >= 18 && citizen == 1)
    {
        printf("Eligible to vote\n");
    }
    else
    {
        printf("Not eligible\n");
    }

    return 0;
}
```

This works because:

```
Both conditions must be true
```

But notice:

This version gives **less detailed feedback**.

The nested version is **more descriptive**.

---

# 🎯 Real-Life Analogy

Think of it like entering a **secured building**.

Security guard checks:

1️⃣ Are you **18 or older**?  
2️⃣ Are you an **authorized member**?

If both are satisfied → **You enter**

If either fails → **Entry denied**

---

# 🧠 Deep Understanding Summary

Nested `if` is used when:

- One condition **depends on another**
- We need **detailed decision paths**
- We want **structured logical flow**

---

# 🧩 Mini Challenge

Modify the program to:

- Take **age as user input**
- Take **citizen status as input (1 or 0)**
- Print **detailed messages**

---

# 🚀 What You Just Learned

You now understand:

- Nested `if` execution flow
- Step-by-step evaluation
- How the program moves inside blocks
- Real-life conditional modeling
- Alternative using logical operators

This is how programs begin to **think logically**.

# ⚠️ Common Beginner Mistakes

## Missing Braces

Bad practice:

```c
if(age >= 18)
printf("Adult");
```

Better practice:

```c
if(age >= 18)
{
    printf("Adult");
}
```

---

## Using `=` instead of `==`

Wrong:

```c
if(a = 5)
```

Correct:

```c
if(a == 5)
```

---

# 📊 Comparison Operators Used in Conditions

| Operator | Meaning |
|----------|--------|
| `==` | Equal |
| `!=` | Not equal |
| `>` | Greater |
| `<` | Less |
| `>=` | Greater or equal |
| `<=` | Less or equal |

---

# 🧩 Practice Exercises

## 1️⃣ Even or Odd

Write a program that checks whether a number is **even or odd**.

---

## 2️⃣ Largest Number

Input two numbers and print the **largest**.

---

## 3️⃣ Voting Eligibility

Ask the user for their age and print:

```
Eligible to vote
```

or

```
Not eligible
```

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

int main()
{
    int x = 5;

    if(x > 10)
        printf("A\n");
    else if(x > 3)
        printf("B\n");
    else
        printf("C\n");

    return 0;
}
```

---

# Try Before Looking

```
x = 5
Check conditions carefully.
```

---

# ✅ Solution

Condition 1:

```
x > 10 → false
```

Condition 2:

```
x > 3 → true
```

So this executes:

```c
printf("B");
```

---

# Final Output

```
B
```

---

# 🧠 Key Takeaways

From this chapter you learned:

- `if` statements
- `if-else`
- `else if`
- nested conditions
- comparison operators
- decision making logic

Control flow allows programs to **choose different paths based on conditions**.

---

# 🚀 Next Chapter

Next we will explore:

# Loops in C

Where we will learn:

- `for` loop
- `while` loop
- `do-while` loop

Loops allow programs to **repeat tasks efficiently**.
