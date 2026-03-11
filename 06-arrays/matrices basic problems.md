# 📘 C Programming – Matrix Concepts & Problems

Matrices in C are stored using **2D arrays**.

Example declaration:

```c
int matrix[3][3];
```

Meaning:

```
3 rows
3 columns
```

---

# Visual Representation

```
      Column
        ↓
      0   1   2
    ┌───┬───┬───┐
0 → │ 1 │ 2 │ 3 │
    ├───┼───┼───┤
1 → │ 4 │ 5 │ 6 │
    ├───┼───┼───┤
2 → │ 7 │ 8 │ 9 │
    └───┴───┴───┘
        ↑
       Row
```

Access pattern:

```
matrix[row][column]
```

Example:

```
matrix[1][2]
→ row 1
→ column 2
```

---

# 1️⃣ Matrix Input

Read elements into a matrix using **nested loops**.

## Program

```c
#include <stdio.h>

int main()
{
    int matrix[3][3];

    printf("Enter 9 numbers:\n");

    for(int i=0;i<3;i++)
    {
        for(int j=0;j<3;j++)
        {
            scanf("%d",&matrix[i][j]);
        }
    }

    return 0;
}
```

## Key Idea

```
Outer loop → rows
Inner loop → columns
```

```
i = row
j = column
```

Matrix filling order:

```
matrix[0][0]
matrix[0][1]
matrix[0][2]

matrix[1][0]
matrix[1][1]
matrix[1][2]

matrix[2][0]
matrix[2][1]
matrix[2][2]
```

---

# 2️⃣ Matrix Sum

Add **all elements in a matrix**.

Example:

```
1 2 3
4 5 6
7 8 9
```

Sum:

```
45
```

## Program

```c
#include <stdio.h>

int main()
{
    int matrix[3][3];
    int sum = 0;

    printf("Enter 9 numbers:\n");

    for(int i=0;i<3;i++)
    {
        for(int j=0;j<3;j++)
        {
            scanf("%d",&matrix[i][j]);
            sum += matrix[i][j];
        }
    }

    printf("Sum = %d",sum);

    return 0;
}
```

## Key Logic

```
sum = sum + matrix[i][j]
```

---

# 3️⃣ Main Diagonal Elements

Diagonal elements occur where:

```
row = column
```

Example matrix:

```
1 2 3
4 5 6
7 8 9
```

Diagonal:

```
1 5 9
```

## Program

```c
for(int i=0;i<3;i++)
{
    printf("%d ",matrix[i][i]);
}
```

## Rule

```
matrix[i][i]
```

---

# 4️⃣ Matrix Transpose

Transpose flips **rows into columns**.

Original:

```
1 2 3
4 5 6
7 8 9
```

Transpose:

```
1 4 7
2 5 8
3 6 9
```

## Rule

```
matrix[i][j] → matrix[j][i]
```

## Program

```c
for(int i=0;i<3;i++)
{
    for(int j=0;j<3;j++)
    {
        printf("%d ",matrix[j][i]);
    }
    printf("\n");
}
```

---

# 5️⃣ Matrix Multiplication

Multiply **rows of first matrix** with **columns of second matrix**.

Example:

Matrix A

```
1 2
3 4
```

Matrix B

```
5 6
7 8
```

Result:

```
19 22
43 50
```

Calculation example:

```
C[0][0] = (1×5) + (2×7) = 19
```

## Program Logic

```c
C[i][j] = 0;

for(int k=0;k<2;k++)
{
    C[i][j] += A[i][k] * B[k][j];
}
```

## Important Reason for

```
C[i][j] = 0
```

Because multiplication results are **added step by step**.

Example:

```
0 + (1×5) + (2×7)
```

If not initialized:

```
memory may contain garbage values
```

---

# 6️⃣ Symmetric Matrix

A matrix is **symmetric** if it equals its transpose.

## Rule

```
matrix[i][j] = matrix[j][i]
```

Example symmetric matrix:

```
1 2 3
2 4 5
3 5 6
```

Mirror across diagonal.

---

## Basic Logic

Assume symmetric

If mismatch found → **not symmetric**

## Program

```c
int symmetric = 1;

for(int i=0;i<3;i++)
{
    for(int j=0;j<3;j++)
    {
        if(matrix[i][j] != matrix[j][i])
        {
            symmetric = 0;
        }
    }
}
```

Flag meaning:

```
1 → symmetric
0 → not symmetric
```

---

# Optimized Method (Half Comparisons)

We only check **upper triangle**.

```c
for(int j = i + 1; j < n; j++)
```

Improved code:

```c
for(int i=0;i<3;i++)
{
    for(int j=i+1;j<3;j++)
    {
        if(matrix[i][j] != matrix[j][i])
        {
            symmetric = 0;
            break;
        }
    }
}
```

Reason:

```
Lower half is mirror of upper half
```

---

# 7️⃣ Upper Triangle Matrix

Upper triangle contains elements **on or above the diagonal**.

Example:

```
1 2 3
0 5 6
0 0 9
```

## Rule

```
i ≤ j
```

## Program

```c
if(i <= j)
    printf("%d ",matrix[i][j]);
else
    printf("0 ");
```

---

# 8️⃣ Lower Triangle Matrix

Lower triangle contains elements **on or below the diagonal**.

Example:

```
1 0 0
4 5 0
7 8 9
```

## Rule

```
i ≥ j
```

## Program

```c
if(i >= j)
    printf("%d ",matrix[i][j]);
else
    printf("0 ");
```

---

# 🧠 Important Matrix Rules

| Concept | Rule |
|-------|------|
| Matrix indexing | `matrix[row][column]` |
| Diagonal | `i == j` |
| Upper triangle | `i ≤ j` |
| Lower triangle | `i ≥ j` |
| Transpose | `matrix[i][j] → matrix[j][i]` |
| Symmetric | `matrix[i][j] == matrix[j][i]` |
| Multiplication | `C[i][j] += A[i][k] * B[k][j]` |

---

# 🧩 Programming Patterns Used

Most matrix programs follow this structure:

```
for rows
    for columns
        process matrix element
```

Key concepts used:

- 2D arrays
- nested loops
- indexing
- conditional checks
- accumulation (`+=`)
- flag variables

---

# ⭐ Matrix Problems Covered

- Matrix input
- Matrix sum
- Diagonal elements
- Matrix transpose
- Matrix multiplication
- Symmetric matrix check
- Upper triangle matrix
- Lower triangle matrix
