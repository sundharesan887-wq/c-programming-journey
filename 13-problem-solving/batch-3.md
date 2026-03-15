# C Programming Problem Solving Journey
## Batch 3 — Problems 11 to 15

This batch covers:

- Character input
- ASCII logic
- Logical operators
- Basic mathematical algorithms

---

# Problem 11 — Divisible by 5 and 11

## Question

Write a C program that checks whether a number is divisible by **both 5 and 11**.

## Example Input/Output

```
Input:
55

Output:
Number is divisible by 5 and 11
```

```
Input:
20

Output:
Number is not divisible by 5 and 11
```

---

## Hint

Use the remainder operator:

```
number % 5
number % 11
```

Both must be **0**.

Use logical AND:

```
&&
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

    if (number % 5 == 0 && number % 11 == 0)
        printf("Number is divisible by 5 and 11\n");
    else
        printf("Number is not divisible by 5 and 11\n");

    return 0;
}
```

## Explanation

Example:

```
55 % 5 = 0
55 % 11 = 0
```

Both conditions are true → divisible.

---

# Problem 12 — ASCII Value of a Character

## Question

Write a program to print the ASCII value of a character.

## Example Input/Output

```
Input:
A

Output:
ASCII value = 65
```

---

## Hint

A character internally is stored as an integer ASCII value.

So printing it with `%d` reveals its ASCII code.

---

## Answer

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    printf("ASCII value = %d\n", ch);

    return 0;
}
```

## Explanation

Example ASCII values:

```
'A' → 65
'a' → 97
'0' → 48
```

When printed with `%d`, the computer shows the ASCII code.

---

# Problem 13 — Check Alphabet, Digit, or Special Character

## Question

Write a program to check whether a character is:

- Alphabet
- Digit
- Special character

---

## Example Input/Output

```
Input:
A

Output:
Alphabet
```

```
Input:
5

Output:
Digit
```

```
Input:
@

Output:
Special character
```

---

## Hint

ASCII ranges:

```
A–Z → 65–90
a–z → 97–122
0–9 → 48–57
```

---

## Answer

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    if ((ch >= 'A' && ch <= 'Z') || (ch >= 'a' && ch <= 'z'))
        printf("Alphabet\n");

    else if (ch >= '0' && ch <= '9')
        printf("Digit\n");

    else
        printf("Special character\n");

    return 0;
}
```

## Explanation

Characters are stored using ASCII numbers.

Example:

```
'A' = 65
'B' = 66
'a' = 97
'0' = 48
```

The program checks if the character falls within these ranges.

---

# Problem 14 — Vowel or Consonant

## Question

Write a C program that checks whether an alphabet is a **vowel or consonant**.

---

## Example Input/Output

```
Input:
a

Output:
Vowel
```

```
Input:
b

Output:
Consonant
```

---

## Hint

Vowels are:

```
a e i o u
A E I O U
```

---

## Answer

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter an alphabet: ");
    scanf(" %c", &ch);

    if (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u'||
        ch=='A'||ch=='E'||ch=='I'||ch=='O'||ch=='U')
        printf("Vowel\n");
    else
        printf("Consonant\n");

    return 0;
}
```

---

## Alternative — Convert to Lowercase

```c
#include <stdio.h>
#include <ctype.h>

int main()
{
    char ch;

    printf("Enter an alphabet: ");
    scanf(" %c", &ch);

    ch = tolower(ch);

    if (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u')
        printf("Vowel\n");
    else
        printf("Consonant\n");

    return 0;
}
```

This avoids checking uppercase separately.

---

# Problem 15 — Sum of First N Natural Numbers

## Question

Write a program to find the sum of the first **N natural numbers**.

---

## Example Input/Output

```
Input:
5

Output:
Sum = 15
```

Because:

```
1 + 2 + 3 + 4 + 5 = 15
```

---

## Hint

You need a loop.

Add numbers from:

```
1 → N
```

---

## Answer (Loop Method)

```c
#include <stdio.h>

int main()
{
    int n, i, sum = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++)
    {
        sum = sum + i;
    }

    printf("Sum = %d\n", sum);

    return 0;
}
```

---

## Alternative — Mathematical Formula

There is a famous formula:

```
Sum = n(n+1) / 2
```

```c
#include <stdio.h>

int main()
{
    int n, sum;

    printf("Enter a number: ");
    scanf("%d", &n);

    sum = n*(n+1)/2;

    printf("Sum = %d\n", sum);

    return 0;
}
```

This is **O(1) time complexity** instead of a loop.

---

# Time Complexity in Algorithms

Understanding time complexity helps us measure how efficient an algorithm is as the input size grows.

Instead of measuring exact seconds, computer scientists measure **how the number of operations grows** with input size.

This is represented using **Big-O notation**.

---

# What is Time Complexity?

Time complexity describes **how the running time of a program changes when the input size increases**.

Example:

If input becomes bigger, does the program take **more steps** to finish?

Big-O notation helps us describe this growth.

Example notations:

```
O(1)
O(n)
O(n²)
O(log n)
```

---

# O(1) — Constant Time

An algorithm is **O(1)** when it always takes the same number of operations regardless of input size.

Example:

```c
sum = n*(n+1)/2;
```

Operations performed:

- 1 multiplication  
- 1 addition  
- 1 division  

Even if:

```
n = 5
n = 1000
n = 1,000,000
```

The program still performs the **same number of steps**.

This is called **constant time complexity**.

---

# O(n) — Linear Time

An algorithm is **O(n)** when the number of operations grows proportionally with the input size.

Example:

```c
for(int i = 0; i < n; i++)
{
    printf("%d", i);
}
```

If:

```
n = 5
```

Loop runs **5 times**.

If:

```
n = 100
```

Loop runs **100 times**.

If:

```
n = 1,000,000
```

Loop runs **1,000,000 times**.

So the running time grows **linearly with n**.

---

# Example Comparison

## Problem

Sum of first **N natural numbers**.

Example:

```
1 + 2 + 3 + 4 + 5 = 15
```

---

## Loop Method

```c
sum = 0;

for(int i = 1; i <= n; i++)
{
    sum += i;
}
```

Time complexity:

```
O(n)
```

Because the loop runs **n times**.

---

## Mathematical Formula

```c
sum = n*(n+1)/2;
```

Time complexity:

```
O(1)
```

Because it uses **constant operations**.

---

# Visual Comparison

| Method | Operations for n=5 | Operations for n=1,000,000 |
|------|--------------------|----------------------------|
| Loop | 5 | 1,000,000 |
| Formula | 3 | 3 |

The formula is **far more efficient** for very large inputs.

---

# Why Time Complexity Matters

When programs handle large data:

- inefficient algorithms become **extremely slow**
- efficient algorithms remain **fast**

Example:

If a program runs **1 billion operations**, it may take several seconds or minutes.

If it runs **3 operations**, it finishes almost instantly.

---

# Common Time Complexities

| Complexity | Name | Example |
|------------|------|--------|
| O(1) | Constant | Direct calculation |
| O(log n) | Logarithmic | Binary search |
| O(n) | Linear | Single loop |
| O(n²) | Quadratic | Nested loops |

---

# Key Takeaway

Efficient algorithms try to **minimize the number of operations** as input size grows.

In general:

```
O(1)  is faster than O(n)
O(n)  is faster than O(n²)
```

Understanding **time complexity** is the foundation of **algorithm design and problem solving**.

# Summary of Batch 3

## Concepts Learned

- ASCII values
- Character ranges
- Logical operators
- Character classification
- Mathematical formulas
- First algorithm optimization (**O(n) → O(1)**)
- Time complexity
