# 📊 Multidimensional Arrays in C

So far we learned **one-dimensional arrays**.

Example:

```c
int numbers[5];
```

This stores values in a **single row**.

But sometimes we need data in **rows and columns**.

Examples:

- student marks table
- matrices in mathematics
- game boards
- spreadsheets

For this we use **multidimensional arrays**.

---

# 🧠 What is a Multidimensional Array?

A **multidimensional array** is an array containing **multiple arrays**.

The most common type is a **2D array**.

Example:

```c
int matrix[3][3];
```

This creates:

```
3 rows
3 columns
```

---

# 📦 Memory Representation

```
Column →   0   1   2

Row 0     [ ] [ ] [ ]
Row 1     [ ] [ ] [ ]
Row 2     [ ] [ ] [ ]
```

Each element is accessed using:

```
array[row][column]
```

Example:

```
matrix[1][2]
```

means:

```
row 1
column 2
```

---

# 📌 Declaring a 2D Array

## Syntax

```c
datatype array_name[rows][columns];
```

## Example

```c
int matrix[2][3];
```

This creates:

```
2 rows
3 columns
```

Total elements:

```
2 × 3 = 6
```

---

# 📌 Initializing a 2D Array

Example:

```c
int matrix[2][3] =
{
    {1,2,3},
    {4,5,6}
};
```

Memory layout:

```
Row 0 → 1 2 3
Row 1 → 4 5 6
```

---

# 📌 Accessing Elements

Examples:

```
matrix[0][0] → 1
matrix[0][1] → 2
matrix[1][2] → 6
```

---

# Example Program

```c
#include <stdio.h>

int main()
{
    int matrix[2][3] =
    {
        {1,2,3},
        {4,5,6}
    };

    printf("%d\n", matrix[0][1]);
    printf("%d\n", matrix[1][2]);

    return 0;
}
```

---

# Output

```
2
6
```

---

# 🔁 Using Nested Loops with 2D Arrays

Since 2D arrays have **rows and columns**, we use **nested loops**.

Example:

```c
#include <stdio.h>

int main()
{
    int matrix[2][3] =
    {
        {1,2,3},
        {4,5,6}
    };

    int i, j;

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 3; j++)
        {
            printf("%d ", matrix[i][j]);
        }

        printf("\n");
    }

    return 0;
}
```

---

# Output

```
1 2 3
4 5 6
```

---

# Step-by-Step Execution

Initial values:

```
i = 0
j = 0
```

First row:

```
matrix[0][0] → 1
matrix[0][1] → 2
matrix[0][2] → 3
```

Second row:

```
matrix[1][0] → 4
matrix[1][1] → 5
matrix[1][2] → 6
```

---

# 📥 Taking Matrix Input

Example:

```c
#include <stdio.h>

int main()
{
    int matrix[2][2];
    int i, j;

    printf("Enter matrix values:\n");

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 2; j++)
        {
            scanf("%d", &matrix[i][j]);
        }
    }

    printf("Matrix:\n");

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 2; j++)
        {
            printf("%d ", matrix[i][j]);
        }

        printf("\n");
    }

    return 0;
}
```

---

# Example Input

```
1 2
3 4
```

---

# Output

```
1 2
3 4
```

---

# 📊 Matrix Addition Example

Example program:

```c
#include <stdio.h>

int main()
{
    int A[2][2] = {{1,2},{3,4}};
    int B[2][2] = {{5,6},{7,8}};
    int C[2][2];

    int i, j;

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 2; j++)
        {
            C[i][j] = A[i][j] + B[i][j];
        }
    }

    printf("Result Matrix:\n");

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 2; j++)
        {
            printf("%d ", C[i][j]);
        }

        printf("\n");
    }

    return 0;
}
```

---

# Output

```
6 8
10 12
```

---

# ⚠ Common Beginner Mistakes

## Wrong Index Access

Wrong:

```
matrix[2][2]
```

For a **2×2 array** valid indices are:

```
0 and 1
```

Accessing outside bounds causes **undefined behavior**.

---

# 🧩 Practice Exercises

## 1️⃣ Matrix Input

Write a program that reads a **3×3 matrix** from the user.

---

## 2️⃣ Matrix Sum

Calculate the **sum of all elements in a matrix**.

---

## 3️⃣ Matrix Diagonal

Print the **main diagonal elements**.

Example:

```
1 2 3
4 5 6
7 8 9
```

Output:

```
1 5 9
```

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

int main()
{
    int arr[2][2] = {{1,2},{3,4}};
    int i, j, sum = 0;

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 2; j++)
        {
            sum += arr[i][j];
        }
    }

    printf("%d\n", sum);

    return 0;
}
```

---

# Try Before Looking

Track how `sum` changes.

---

# ✅ Solution

Array elements:

```
1 2
3 4
```

Execution:

```
sum = 0
sum = 0 + 1 = 1
sum = 1 + 2 = 3
sum = 3 + 3 = 6
sum = 6 + 4 = 10
```

---

# Final Output

```
10
```

---

# 🧠 Key Takeaways

You learned:

- multidimensional arrays
- row and column indexing
- nested loops with arrays
- matrix operations

2D arrays are used in **graphics, data tables, and mathematical computations**.

---

# 🚀 Next Chapter

Next we will explore:

# Strings in C

Topics include:

- character arrays
- string input/output
- string functions
