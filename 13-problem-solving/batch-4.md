# C Programming Problem Solving Journey
## Batch 4 — Problems 16 to 20

This batch covers:

- Loop fundamentals
- Mathematical algorithms
- Digit manipulation
- Basic number analysis

---

# Problem 16 — Multiplication Table

## Question

Write a C program to print the multiplication table of a given number.

## Example Input/Output

```
Input:
5

Output:

5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
5 x 4 = 20  
5 x 5 = 25  
5 x 6 = 30  
5 x 7 = 35  
5 x 8 = 40  
5 x 9 = 45  
5 x 10 = 50  
```

---

## Hint

Use a loop from:

```
1 → 10
```

Multiply each value with the number.

---

## Answer

```c
#include <stdio.h>

int main()
{
    int n, i;

    printf("Enter a number: ");
    scanf("%d", &n);

    for(i = 1; i <= 10; i++)
    {
        printf("%d x %d = %d\n", n, i, n*i);
    }

    return 0;
}
```

## Explanation

Example for `n = 5`

Loop runs from **1 to 10**.

Each iteration computes:

```
n * i
```

Example:

```
5 * 1
5 * 2
5 * 3
...
```

### Time Complexity

```
O(1)
```

Because the loop always runs **10 times**.

---

# Problem 17 — Factorial of a Number

## Question

Write a program to calculate the factorial of a number.

### Factorial Definition

```
n! = n × (n-1) × (n-2) × ... × 1
```

Example:

```
5! = 5 × 4 × 3 × 2 × 1 = 120
```

---

## Example Input/Output

```
Input:
5

Output:
Factorial = 120
```

---

## Hint

Use a loop:

```
1 → n
```

Multiply the values.

---

## Answer

```c
#include <stdio.h>

int main()
{
    int n, i;
    long long factorial = 1;

    printf("Enter a number: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++)
    {
        factorial = factorial * i;
    }

    printf("Factorial = %lld\n", factorial);

    return 0;
}
```

## Explanation

Example `n = 5`

```
factorial = 1
1 × 1 = 1
1 × 2 = 2
2 × 3 = 6
6 × 4 = 24
24 × 5 = 120
```

### Time Complexity

```
O(n)
```

---

## Alternative — Recursive Method

```c
#include <stdio.h>

long long factorial(int n)
{
    if(n == 0 || n == 1)
        return 1;

    return n * factorial(n-1);
}
```

---

# Problem 18 — Reverse a Number

## Question

Write a program to reverse the digits of a number.

---

## Example Input/Output

```
Input:
1234

Output:
4321
```

---

## Hint

Use:

```
% 10  → extract digit
/ 10  → remove digit
```

---

## Answer

```c
#include <stdio.h>

int main()
{
    int n, reverse = 0, digit;

    printf("Enter a number: ");
    scanf("%d", &n);

    while(n != 0)
    {
        digit = n % 10;
        reverse = reverse * 10 + digit;
        n = n / 10;
    }

    printf("Reversed number = %d\n", reverse);

    return 0;
}
```

## Explanation

Example `1234`

```
digit = 4 → reverse = 4
digit = 3 → reverse = 43
digit = 2 → reverse = 432
digit = 1 → reverse = 4321
```

### Time Complexity

```
O(d)
```

Where `d = number of digits`.

---

# Problem 19 — Count Digits in a Number

## Question

Write a program to count the number of digits in an integer.

---

## Example Input/Output

```
Input:
5489

Output:
Number of digits = 4
```

---

## Hint

Divide the number repeatedly by 10.

---

## Answer

```c
#include <stdio.h>

int main()
{
    int n, count = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    while(n != 0)
    {
        n = n / 10;
        count++;
    }

    printf("Number of digits = %d\n", count);

    return 0;
}
```

## Explanation

Example:

```
5489 → 548
548  → 54
54   → 5
5    → 0
```

Total steps = **4 digits**.

### Time Complexity

```
O(d)
```

---

# Problem 20 — Palindrome Number

## Question

Write a program to check whether a number is a palindrome.

A palindrome reads the same forwards and backwards.

---

## Example Input/Output

```
Input:
121

Output:
Palindrome
```

```
Input:
123

Output:
Not a palindrome
```

---

## Hint

- Reverse the number  
- Compare with original  

---

## Answer

```c
#include <stdio.h>

int main()
{
    int n, original, reverse = 0, digit;

    printf("Enter a number: ");
    scanf("%d", &n);

    original = n;

    while(n != 0)
    {
        digit = n % 10;
        reverse = reverse * 10 + digit;
        n = n / 10;
    }

    if(original == reverse)
        printf("Palindrome\n");
    else
        printf("Not a palindrome\n");

    return 0;
}
```

---

# Summary of Batch 4

## Concepts Learned

- Loop control  
- Digit extraction  
- Number manipulation  
- Reverse algorithms  
- Palindrome logic  

---

## Key Operations Introduced

```
% 10   → extract last digit
/ 10   → remove last digit
```

These operations are **fundamental for many algorithm problems**.
