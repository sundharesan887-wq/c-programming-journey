# C Programming Problem Solving Journey
## Batch 1 — Problems 1 to 5

This batch covers:

- Basic input/output
- Variables
- Arithmetic
- Even/Odd logic
- Swapping values

---

# Problem 1 — Echo a Number

## Question

Write a C program that asks the user to enter a number and prints the same number back.

## Example Input/Output

```
Input:
7

Output:
You entered: 7
```

## Hint

- Create one integer variable
- Use `scanf()` to take input
- Use `printf()` to display it

---

## Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    printf("You entered: %d\n", number);

    return 0;
}
```

## Explanation

- `int number;` creates a box to store one integer  
- `scanf("%d", &number);` stores the user’s input inside `number`  
- `printf("You entered: %d\n", number);` prints the value  

## Alternative

There is no major alternative here. This is the standard beginner approach.

---

# Problem 2 — Add Two Numbers

## Question

Write a C program that asks the user to enter two numbers and prints their sum.

## Example Input/Output

```
Input:
5
3

Output:
Sum = 8
```

## Hint

- Create 3 variables: `a`, `b`, `sum`
- Take input for `a` and `b`
- Compute `sum = a + b`

---

## Answer

```c
#include <stdio.h>

int main()
{
    int a, b, sum;

    printf("Enter first number: ");
    scanf("%d", &a);

    printf("Enter second number: ");
    scanf("%d", &b);

    sum = a + b;

    printf("Sum = %d\n", sum);

    return 0;
}
```

## Explanation

- `a` stores the first number  
- `b` stores the second number  
- `sum` stores the result of `a + b`  

The computer adds the values and prints the answer.

## Alternative

You can print directly without storing in `sum`:

```c
printf("Sum = %d\n", a + b);
```

This is shorter, but using `sum` is better for learning.

---

# Problem 3 — Even or Odd

## Question

Write a C program that checks whether a number is even or odd.

## Example Input/Output

```
Input:
8

Output:
Even number
```

```
Input:
7

Output:
Odd number
```

## Hint

- Use `% 2`
- If remainder is `0`, the number is even
- Otherwise it is odd

---

## Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number % 2 == 0)
    {
        printf("Even number\n");
    }
    else
    {
        printf("Odd number\n");
    }

    return 0;
}
```

## Explanation

- `%` gives the remainder  
- `number % 2 == 0` means the number is divisible by 2  
- If divisible, it is even  
- Otherwise, it is odd  

---

## Alternative 1 — Bitwise Method

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number & 1)
    {
        printf("Odd number\n");
    }
    else
    {
        printf("Even number\n");
    }

    return 0;
}
```

### Why this works

In binary:

- Odd numbers end in `1`
- Even numbers end in `0`

`number & 1` checks the last bit.

---

## Alternative 2 — Division Logic

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if ((number / 2) * 2 == number)
    {
        printf("Even number\n");
    }
    else
    {
        printf("Odd number\n");
    }

    return 0;
}
```

This works, but `%` is much clearer.

---

# Problem 4 — Swap Two Numbers Using a Temporary Variable

## Question

Write a C program that swaps two numbers using a temporary variable.

## Example Input/Output

```
Input:
a = 5
b = 10

Output:
a = 10
b = 5
```

## Hint

- Use a third variable called `temp`
- Store one value safely before replacing it

---

## Answer

```c
#include <stdio.h>

int main()
{
    int a, b, temp;

    printf("Enter first number: ");
    scanf("%d", &a);

    printf("Enter second number: ");
    scanf("%d", &b);

    temp = a;
    a = b;
    b = temp;

    printf("After swapping:\n");
    printf("First number: %d\n", a);
    printf("Second number: %d\n", b);

    return 0;
}
```

## Explanation

- `temp = a;` saves the first value  
- `a = b;` puts the second value into the first variable  
- `b = temp;` restores the original first value into the second variable  

---

## Alternative

This is the **best and safest method in real programming**.

---

# Problem 5 — Swap Two Numbers Without a Temporary Variable

## Question

Write a C program that swaps two numbers without using a third variable.

## Example Input/Output

```
Input:
a = 5
b = 10

Output:
a = 10
b = 5
```

## Hint

Try using arithmetic or bitwise operators.

---

# Answer 1 — Addition and Subtraction

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter first number: ");
    scanf("%d", &a);

    printf("Enter second number: ");
    scanf("%d", &b);

    a = a + b;
    b = a - b;
    a = a - b;

    printf("After swapping:\n");
    printf("First number: %d\n", a);
    printf("Second number: %d\n", b);

    return 0;
}
```

## Explanation

Suppose:

```
a = 5
b = 10
```

Then:

```
a = a + b → a = 15
b = a - b → b = 5
a = a - b → a = 10
```

### Warning

This can cause **overflow for very large numbers**.

---

# Answer 2 — XOR Swap

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter first number: ");
    scanf("%d", &a);

    printf("Enter second number: ");
    scanf("%d", &b);

    a = a ^ b;
    b = a ^ b;
    a = a ^ b;

    printf("After swapping:\n");
    printf("First number: %d\n", a);
    printf("Second number: %d\n", b);

    return 0;
}
```

## Explanation

XOR properties:

```
x ^ x = 0
x ^ 0 = x
```

This method swaps values without extra memory.

### Warning

Good for learning **bitwise logic**, but the temporary variable method is usually better for readability.

---

# Answer 3 — Pointer Swap Through Function

```c
#include <stdio.h>

void swap(int *x, int *y)
{
    int temp = *x;
    *x = *y;
    *y = temp;
}

int main()
{
    int a, b;

    printf("Enter first number: ");
    scanf("%d", &a);

    printf("Enter second number: ");
    scanf("%d", &b);

    swap(&a, &b);

    printf("After swapping:\n");
    printf("First number: %d\n", a);
    printf("Second number: %d\n", b);

    return 0;
}
```

## Explanation

- `&a` means address of `a`
- `&b` means address of `b`

The function receives those addresses.

Using pointers, it changes the **original variables directly**.

### Why this matters

This is the **real foundation for pointer-based programming**.

---

# Summary of Batch 1

## Concepts Learned

- Input and output
- Variables
- Arithmetic
- Remainder operator
- Even/Odd checking
- Swapping
- Bitwise XOR
- Pointer-based swapping
