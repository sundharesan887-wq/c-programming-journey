# 🔤 Strings in C

Programs often need to work with **text data**.

Examples:

- names  
- addresses  
- messages  
- passwords  

In C, text is stored using **strings**.

---

# 🧠 What is a String?

A **string** is a sequence of characters stored in an array.

Example:

```c
char name[6] = "Alice";
```

This stores the characters:

```
A l i c e
```

But C also stores a special character at the end.

```
'\0'
```

This is called the **null character**.

It marks the **end of the string**.

---

# 📦 Memory Representation

Example:

```c
char name[6] = "Alice";
```

Memory layout:

| Index | Character |
|------|-----------|
| 0 | A |
| 1 | l |
| 2 | i |
| 3 | c |
| 4 | e |
| 5 | \0 |

Important rule:

**All strings in C end with `'\0'`.**

---

# 📌 Declaring a String

## Syntax

```c
char string_name[size];
```

## Example

```c
char name[20];
```

This can store up to **19 characters**.

The last space is reserved for:

```
'\0'
```

---

# 📌 Initializing Strings

## Method 1

```c
char name[] = "Alice";
```

## Method 2

```c
char name[6] = {'A','l','i','c','e','\0'};
```

Both create the **same string**.

---

# 🖥 Printing Strings

We use `printf()`.

Example:

```c
#include <stdio.h>

int main()
{
    char name[] = "Alice";

    printf("%s\n", name);

    return 0;
}
```

## Output

```
Alice
```

`%s` is the **string format specifier**.

---

# 📥 Reading Strings

Example:

```c
#include <stdio.h>

int main()
{
    char name[20];

    printf("Enter your name: ");
    scanf("%s", name);

    printf("Hello %s\n", name);

    return 0;
}
```

---

# ⚠ Limitation of `scanf`

`scanf("%s", name)` stops reading **at space**.

Example input:

```
John Doe
```

Stored value:

```
John
```

To read **full sentences** we use:

```
fgets()
```

---

# Using `fgets()`

Example:

```c
#include <stdio.h>

int main()
{
    char name[50];

    printf("Enter your name: ");
    fgets(name, sizeof(name), stdin);

    printf("Hello %s", name);

    return 0;
}
```

`fgets()` can read **spaces and full lines**.

---

# 📚 String Functions

String functions are defined in:

```c
#include <string.h>
```

---

# Common String Functions

| Function | Purpose |
|---------|---------|
| `strlen()` | Length of string |
| `strcpy()` | Copy string |
| `strcat()` | Concatenate strings |
| `strcmp()` | Compare strings |

---

# 1️⃣ `strlen()`

Finds string length.

Example:

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char text[] = "Hello";

    printf("%lu\n", strlen(text));

    return 0;
}
```

## Output

```
5
```

---

# 2️⃣ `strcpy()`

Copies one string into another.

Example:

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char source[] = "Hello";
    char destination[20];

    strcpy(destination, source);

    printf("%s\n", destination);

    return 0;
}
```

## Output

```
Hello
```

---

# 3️⃣ `strcat()`

Combines two strings.

Example:

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str1[20] = "Hello ";
    char str2[] = "World";

    strcat(str1, str2);

    printf("%s\n", str1);

    return 0;
}
```

## Output

```
Hello World
```

---

# 4️⃣ `strcmp()`

Compares two strings.

Example:

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char a[] = "apple";
    char b[] = "apple";

    printf("%d\n", strcmp(a,b));

    return 0;
}
```

## Output

```
0
```

Meaning:

```
Strings are equal
```

---

# ⚠ Common Beginner Mistakes

## Forgetting Null Character

Wrong:

```c
char name[5] = "Alice";
```

Correct:

Size must include `'\0'`.

---

## Using `==` to Compare Strings

Wrong:

```c
if(str1 == str2)
```

Correct:

```c
strcmp(str1,str2)
```

---

# 🧩 Practice Exercises

## 1️⃣ String Length

Write a program that calculates the **length of a string**.

---

## 2️⃣ String Copy

Copy **one string into another**.

---

## 3️⃣ String Concatenation

Combine **first name and last name**.

Example:

```
Input: John + Doe
Output: John Doe
```

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char a[20] = "Hello";
    char b[] = "World";

    strcat(a, b);

    printf("%s\n", a);

    return 0;
}
```

---

# Try Before Looking

Track how the string changes.

---

# ✅ Solution

Initial string:

```
a = "Hello"
b = "World"
```

After concatenation:

```
HelloWorld
```

---

# Final Output

```
HelloWorld
```

---

# 🧠 Key Takeaways

You learned:

- what strings are
- null terminator
- string input/output
- string functions
- string comparison

Strings are essential for **text processing and user interaction**.

---

# 🚀 Next Chapter

Next we will explore:

# Pointers in C

Topics include:

- memory addresses
- pointer variables
- pointer operations
- pointers with arrays
