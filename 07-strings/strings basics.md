# 📘 C Programming – Strings (Complete Beginner Guide)

In C, a **string** is a sequence of characters stored in a **character array** and ending with a **null character `\0`**.

Example:

```c
char name[] = "Hello";
```

## Memory Representation

```
Index →   0   1   2   3   4   5
        ┌───┬───┬───┬───┬───┬───┐
Data →  H   e   l   l   o  \0
```

The null character `\0` tells C **where the string ends**.

---

# 1️⃣ Declaring Strings

## Method 1 – Using a String Literal

```c
char name[] = "Alice";
```

Memory:

```
A l i c e \0
```

---

## Method 2 – With Fixed Size

```c
char name[20] = "Alice";
```

This creates **extra space for future operations** like concatenation.

Memory:

```
A l i c e \0 _ _ _ _ _ _ ...
```

---

## Method 3 – Character by Character

```c
char name[] = {'A','l','i','c','e','\0'};
```

---

# 2️⃣ Printing Strings

Use `%s` with `printf`.

```c
printf("%s", name);
```

Example output:

```
Alice
```

---

# 3️⃣ Reading Strings

Use `scanf`.

```c
scanf("%s", name);
```

⚠️ Notice we **do not use `&`**.

---

# 4️⃣ Why We Don't Use `&` With Strings

Example:

```c
char name[20];
scanf("%s", name);
```

Reason:

```
name already represents the address of the first character
```

So:

```
name → address of name[0]
```

Alternative equivalent form:

```c
scanf("%s", &name[0]);
```

Both work the same.

---

## Why `&` is Used With Normal Variables

Example:

```c
int age;
scanf("%d", &age);
```

Because:

```
age → value
&age → memory address
```

`scanf()` needs the **address**.

---

# 5️⃣ String Concatenation (`strcat`)

Concatenation means **joining two strings**.

Example:

```c
char str1[20] = "Hello ";
char str2[] = "World";

strcat(str1, str2);
```

Result:

```
Hello World
```

Rule:

```
destination = destination + source
```

## Important Rule

The **destination string must have enough memory**.

Example:

```c
char str1[20] = "Hello ";
```

This leaves space to add `"World"`.

---

# 6️⃣ Why `"Hello "` Works but `"alice"` Didn't

Example 1:

```c
char str1[20] = "Hello ";
char str2[] = "World";
```

Result:

```
Hello World
```

Because `"Hello "` already contains a space.

---

Example 2:

```c
char name[] = "alice";
char names[] = "doe";
```

Result:

```
alicedoe
```

Because there was **no space between them**.

Solution:

```c
strcat(name, " ");
strcat(name, names);
```

---

# 7️⃣ Alternative Method – `sprintf`

Another way to combine strings:

```c
sprintf(name,"%s %s","alice","doe");
```

Result:

```
alice doe
```

---

# 8️⃣ How `strcat()` Works in Memory

Before concatenation:

```
str1
H e l l o _ \0
```

```
str2
W o r l d \0
```

After:

```
H e l l o _ W o r l d \0
```

---

# 9️⃣ String Memory Layout

Example:

```c
char str[] = "Hello";
```

Memory:

```
Address → 100 101 102 103 104 105
Data    →  H   e   l   l   o   \0
```

`str` stores:

```
address of 'H'
```

---

# 🔟 Strings Are Character Arrays

This means we can access characters individually.

Example:

```c
printf("%c", str[0]);
```

Output:

```
H
```

---

# 🧠 Key Rules About Strings

- Strings are **arrays of characters**.
- Strings end with **`\0`**.
- `%s` is used to **print strings**.
- `scanf("%s", str)` reads strings.
- `&` is **not used for string arrays**.
- Strings are stored **continuously in memory**.
- Destination string must have **enough memory for `strcat()`**.
- `strcat()` does **not add spaces automatically**.
- Strings can be accessed using **indexes**.
- Strings behave like **pointers to the first character**.

---

# ⭐ 10 Must-Know Things About Strings in C

1️⃣ Strings end with `\0`.

Without `\0`, the program won't know where the string ends.

---

2️⃣ Strings are arrays.

```c
char name[10];
```

---

3️⃣ String indexing starts at `0`.

```
name[0] → first character
```

---

4️⃣ `%s` prints a string.

```c
printf("%s", name);
```

---

5️⃣ `strlen()` finds length.

```
strlen("hello") = 5
```

---

6️⃣ `strcpy()` copies strings.

```c
strcpy(dest, source);
```

---

7️⃣ `strcat()` joins strings.

```c
strcat(dest, source);
```

---

8️⃣ Strings need extra space for modification.

Example:

```c
char str[20] = "Hello";
```

---

9️⃣ Strings are stored in continuous memory.

```
H e l l o \0
```

---

🔟 Strings behave like pointers.

```
name = &name[0]
```

---

# 🧠 Programming Pattern for Strings

Most string programs follow this idea:

```
read string
process characters
print result
```

Common operations:

- concatenation
- copying
- comparing
- length calculation

---

# 📚 String Functions Used

Header:

```c
#include <string.h>
```

Common functions:

- `strlen()`
- `strcpy()`
- `strcat()`
- `strcmp()`

---

# 📘 C Programming – `printf`, `sprintf`, and `snprintf`

In C, these three functions are used for **formatted output**, but they send the result to different places.

All three functions are declared in:

```c
#include <stdio.h>
```

---

# 1️⃣ `printf()` – Print to Console

`printf()` prints formatted text directly to the **screen**.

## Example

```c
#include <stdio.h>

int main()
{
    printf("Hello World\n");
    return 0;
}
```

## Output

```
Hello World
```

## Visual Flow

```
Program → printf() → Console (screen)
```

---

# 2️⃣ `sprintf()` – Print Into a String

`sprintf()` writes formatted output into a **string variable** instead of printing it.

## Example

```c
#include <stdio.h>

int main()
{
    char str[50];

    sprintf(str, "Hello %s", "World");

    printf("%s\n", str);

    return 0;
}
```

## What Happens Internally

`sprintf()` writes into memory:

```
str = "Hello World"
```

Memory layout:

```
str
H e l l o _ W o r l d \0
```

## Visual Flow

```
Program → sprintf() → String variable → printf() → Console
```

---

# 3️⃣ `snprintf()` – Safe Version of `sprintf()`

`sprintf()` can cause **buffer overflow** if the string is larger than the allocated memory.

Example of a risky situation:

```c
char str[10];
sprintf(str, "Hello World this is unsafe");
```

The string is larger than the array, which can **overwrite memory**.

---

## Safer Alternative

`snprintf()` limits how many characters can be written.

### Syntax

```c
snprintf(destination, size, format, values);
```

### Example

```c
#include <stdio.h>

int main()
{
    char str[10];

    snprintf(str, sizeof(str), "Hello World");

    printf("%s\n", str);

    return 0;
}
```

Now the function **prevents writing beyond the array size**.

---

# 🔍 Comparison Table

| Function | Output Location | Safety |
|----------|----------------|--------|
| `printf()` | Console | Safe |
| `sprintf()` | String variable | Unsafe (possible overflow) |
| `snprintf()` | String variable | Safe |

---

# 🧠 Simple Memory Explanation

Example:

```c
char str[20];
sprintf(str,"Hello");
```

Memory:

```
Address → 100 101 102 103 104 105
Data    →  H   e   l   l   o  \0
```

The variable `str` stores the **address of the first character**.

```
str → address 100
```

---

# ⭐ Easy Way to Remember

```
printf   → print to screen
sprintf  → print into string
snprintf → safe print into string
```

---

# 🚀 Practical Example

```c
#include <stdio.h>

int main()
{
    char message[50];
    int age = 20;

    sprintf(message, "I am %d years old", age);

    printf("%s\n", message);

    return 0;
}
```

## Output

```
I am 20 years old
```

---

# 🧩 Key Takeaways

- `printf()` prints text to the **console**.
- `sprintf()` writes formatted text **into a string**.
- `snprintf()` **prevents memory overflow**.
- All three support format specifiers like `%d`, `%s`, `%f`.
- `snprintf()` is preferred in **modern C for safer programs**.

---

# 📚 When to Use Each

| Use Case | Recommended Function |
|----------|----------------------|
| Display output | `printf()` |
| Build a string | `sprintf()` |
| Safe string formatting | `snprintf()` |
