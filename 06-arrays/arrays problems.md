# 📘 C Array Practice – Beginner Problems

These exercises help understand **arrays, loops, and basic logic in C**.

---

# 1️⃣ Sum of Array Elements

## Problem

Write a program to calculate the **sum of 5 numbers stored in an array**.

## Program

```c
#include <stdio.h>

int main()
{
    int numbers[5];
    int sum = 0;

    printf("Enter 5 numbers:\n");

    for(int i = 0; i < 5; i++)
    {
        scanf("%d", &numbers[i]);
    }

    for(int i = 0; i < 5; i++)
    {
        sum = sum + numbers[i];
    }

    printf("Sum = %d", sum);

    return 0;
}
```

## Key Idea

Read numbers → store in array → add them using a loop.

## Example

```
Input: 1 2 3 4 5
Output: Sum = 15
```

---

# 2️⃣ Find the Largest Element

## Problem

Input **5 numbers** and find the **largest number**.

## Program

```c
#include <stdio.h>

int main()
{
    int numbers[5];
    int largest;

    printf("Enter 5 numbers:\n");

    for(int i = 0; i < 5; i++)
    {
        scanf("%d", &numbers[i]);
    }

    largest = numbers[0];

    for(int i = 1; i < 5; i++)
    {
        if(numbers[i] > largest)
        {
            largest = numbers[i];
        }
    }

    printf("Largest number = %d", largest);

    return 0;
}
```

## Key Idea

1. Assume first element is largest  
2. Compare with other elements  
3. Update if a bigger number is found  

## Example

```
Input: 3 7 2 9 4
Output: Largest number = 9
```

---

# 3️⃣ Reverse an Array

## Problem

Input numbers and print them in **reverse order**.

## Example

```
Input: 1 2 3 4 5
Output: 5 4 3 2 1
```

## Program

```c
#include <stdio.h>

int main()
{
    int numbers[5];

    printf("Enter 5 numbers:\n");

    for(int i = 0; i < 5; i++)
    {
        scanf("%d", &numbers[i]);
    }

    printf("Reversed array:\n");

    for(int i = 4; i >= 0; i--)
    {
        printf("%d ", numbers[i]);
    }

    return 0;
}
```

## Key Idea

Normal order → start index **0** → move forward  
Reverse order → start **last index** → move backward  

Loop used:

```c
for(int i = 4; i >= 0; i--)
```

---

# 🧠 Concepts Learned

- Arrays  
- Array indexing (`numbers[i]`)  
- `for` loops  
- Input using `scanf()`  
- Conditional statements (`if`)  
- Traversing arrays **forward and backward**

---

# ⭐ Beginner Rules to Remember

## Array Index Always Starts from 0

```
numbers[0] → first element
numbers[n-1] → last element
```

## Common Loop Pattern

```c
for(int i = 0; i < n; i++)
```
