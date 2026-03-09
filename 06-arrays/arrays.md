# 📚 Arrays in C

Often programs need to store **many values of the same type**.

Examples:

- marks of 50 students  
- temperatures for a week  
- prices of products  

Without arrays we would need many variables:

```c
int mark1, mark2, mark3, mark4, mark5;
```

This quickly becomes messy.

Arrays solve this problem.

---

# 🧠 What is an Array?

An **array** is a collection of elements of the **same data type stored in contiguous memory locations**.

Example:

```c
int marks[5];
```

This creates an array that can store **5 integers**.

---

# 📦 Array Memory Representation

```
Index:   0   1   2   3   4
Value:  [ ] [ ] [ ] [ ] [ ]
```

Important rule:

**Array indexing starts from 0**

So an array of size **5** has indices:

- `0` → first element  
- `1` → second element  
- `2` → third element  
- `3` → fourth element  
- `4` → fifth element  

---

# 📌 Declaring an Array

## Syntax

```c
datatype array_name[size];
```

## Example

```c
int numbers[5];
```

Meaning:

- datatype → `int`  
- array name → `numbers`  
- size → **5 elements**

---

# 📌 Initializing an Array

We can assign values while creating the array.

Example:

```c
int numbers[5] = {10, 20, 30, 40, 50};
```

Memory representation:

```
Index:   0   1   2   3   4
Value:  10  20  30  40  50
```

---

# 📌 Accessing Array Elements

Array elements are accessed using **index numbers**.

Examples:

```
numbers[0]
numbers[1]
numbers[2]
```

---

# Example Program

```c
#include <stdio.h>

int main()
{
    int numbers[5] = {10,20,30,40,50};

    printf("%d\n", numbers[0]);
    printf("%d\n", numbers[1]);
    printf("%d\n", numbers[2]);

    return 0;
}
```

---

# Output

```
10
20
30
```

---

# 🔁 Using Loops with Arrays

Arrays are commonly used with **loops**.

Example:

```c
#include <stdio.h>

int main()
{
    int numbers[5] = {10,20,30,40,50};
    int i;

    for(i = 0; i < 5; i++)
    {
        printf("%d\n", numbers[i]);
    }

    return 0;
}
```

---

# Step-by-Step Execution

Initial value:

```
i = 0
```

Loop condition:

```
i < 5
```

Execution:

```
i = 0 → print numbers[0] → 10
i = 1 → print numbers[1] → 20
i = 2 → print numbers[2] → 30
i = 3 → print numbers[3] → 40
i = 4 → print numbers[4] → 50
i = 5 → loop stops
```

---

# 📥 Taking Array Input

Example program:

```c
#include <stdio.h>

int main()
{
    int numbers[5];
    int i;

    printf("Enter 5 numbers:\n");

    for(i = 0; i < 5; i++)
    {
        scanf("%d", &numbers[i]);
    }

    printf("Numbers entered:\n");

    for(i = 0; i < 5; i++)
    {
        printf("%d\n", numbers[i]);
    }

    return 0;
}
```

---

# Example Input

```
10
20
30
40
50
```

---

# Output

```
10
20
30
40
50
```

---

# ⚠ Common Beginner Mistakes

## Accessing Invalid Index

Wrong:

```c
numbers[5]
```

Valid indices are:

```
0 to 4
```

Accessing invalid memory causes **undefined behavior**.

---

# 📊 Array Size Using `sizeof()`

Example:

```c
int numbers[5];

printf("%lu", sizeof(numbers));
```

Explanation:

```
int = 4 bytes
array size = 5 × 4 = 20 bytes
```

---

# 🧩 Practice Exercises

## 1️⃣ Sum of Array

Write a program that calculates the **sum of 5 numbers stored in an array**.

---

## 2️⃣ Find Largest Element

Input **5 numbers** and find the **largest value**.

---

## 3️⃣ Reverse Array

Input numbers and print them in **reverse order**.

Example:

```
Input: 1 2 3 4 5
Output: 5 4 3 2 1
```

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

int main()
{
    int arr[5] = {2,4,6,8,10};
    int i, sum = 0;

    for(i = 0; i < 5; i++)
    {
        sum += arr[i];
    }

    printf("%d\n", sum);

    return 0;
}
```

---

# Try Before Looking

Follow how `sum` changes.

---

# ✅ Solution

Array values:

```
2 4 6 8 10
```

Execution:

```
sum = 0

sum = 0 + 2 = 2
sum = 2 + 4 = 6
sum = 6 + 6 = 12
sum = 12 + 8 = 20
sum = 20 + 10 = 30
```

---

# Final Output

```
30
```

---

# 🧠 Key Takeaways

You learned:

- array declaration
- array initialization
- indexing
- loops with arrays
- memory representation

Arrays allow programs to **store multiple related values efficiently**.

---

# 🚀 Next Chapter

Next we will learn:

# Multidimensional Arrays

Topics include:

- 2D arrays  
- matrix representation  
- nested loops with arrays
