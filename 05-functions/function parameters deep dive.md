# 📘 C Programming Learning Notes – Functions, Return, and Important Concepts

This document summarizes important concepts learned while practicing **C functions and return values**, along with several small tricks and beginner tips.

---

# 1️⃣ Understanding Functions in C

A **function** is a block of code that performs a specific task.

## Example

```c
#include <stdio.h>

int square(int x) {
    int square = x * x;
    return square;
}

int main() {
    int result = square(5);
    printf("%d", result);
    return 0;
}
```

## Output

```
25
```

## Execution Flow

```
main()
   ↓
square(5)
   ↓
5 * 5 = 25
   ↓
return 25
   ↓
printf prints 25
```

---

# 2️⃣ Why `return` is Important

The `return` statement:

- Sends a value back to the caller.
- Immediately stops the function.

## Example

```c
int square(int x) {
    return x * x;
}
```

Without `return`, the function does **not send any value back**.

---

# 3️⃣ What Happens If We Remove `return`?

## Example

```c
int square(int x) {
    int square = x * x;
}
```

This function declares it will **return an `int` but never returns one**.

Result:

**Undefined Behavior**

Possible outputs:

```
25
0
random numbers
```

The program might appear to work sometimes because the **CPU register still holds a value**.

---

# 4️⃣ Example Demonstrating Undefined Behavior

```c
#include <stdio.h>

int magic() {
    int a = 10;
}

int main() {
    printf("%d", magic());
}
```

Possible outputs:

```
10
0
random numbers
```

Because the function **never explicitly returns a value**.

---

# 5️⃣ Golden Rule for Functions

If a function type is:

- `int`
- `float`
- `char`
- `double`

You **must return a value**.

## Example

```c
int add(int a, int b) {
    return a + b;
}
```

---

# 6️⃣ When `return` is Not Required

If the function type is `void`.

## Example

```c
void greet() {
    printf("Hello");
}
```

`void` means **nothing is returned**.

---

# 7️⃣ Famous C Trick – Multiple Returns

```c
#include <stdio.h>

int fun() {
    return 5;
    return 10;
}

int main() {
    printf("%d", fun());
}
```

## Output

```
5
```

Because once `return` executes, the function **immediately stops**.

---

# 8️⃣ Finding the Largest Number Using a Function

## Example

```c
#include <stdio.h>

int fun(int a, int b) {
    if(a > b)
        return a;
    else
        return b;
}

int main() {
    int largest = fun(10,5);
    printf("%d", largest);
    return 0;
}
```

## Output

```
10
```

---

# 9️⃣ Professional Version Using Ternary Operator

Instead of writing an `if-else` block:

```c
if(a>b)
    return a;
else
    return b;
```

We can write:

```c
return (a>b) ? a : b;
```

## Full Example

```c
#include <stdio.h>

int max(int a,int b) {
    return (a>b) ? a : b;
}

int main() {
    printf("%d", max(10,5));
}
```

---

# 🔟 Nested Function Calls

Functions can be **called inside other functions**.

## Example

```c
#include <stdio.h>

int max(int a, int b)
{
    return (a > b) ? a : b;
}

int main()
{
    printf("%d", max(10, max(20,5)));
}
```

## Output

```
20
```

## Execution Flow

```
max(20,5) = 20
max(10,20) = 20
```

---

# 1️⃣1️⃣ Undefined Behavior with `++`

## Example

```c
#include <stdio.h>

int main()
{
    int x = 5;

    printf("%d %d %d", x, x++, ++x);
}
```

This program has **undefined behavior**.

### Reason

`x` is modified **multiple times in the same statement**.

Possible outputs vary depending on compiler.

---

## Correct Way

```c
printf("%d ", x);
printf("%d ", x++);
printf("%d ", ++x);
```

### Output

```
5 5 7
```

---

# 1️⃣2️⃣ Small Useful C Tricks

## 1. `sizeof` Operator

```c
printf("%lu", sizeof(int));
```

Shows the **memory size of a datatype**.

---

## 2. Swap Without Third Variable

```c
a = a + b;
b = a - b;
a = a - b;
```

---

## 3. Even or Odd

Normal method:

```c
if(n % 2 == 0)
```

Bitwise method:

```c
if(n & 1)
```

---

## 4. Shortest Square Function

```c
int square(int x) {
    return x*x;
}
```

---

## 5. Infinite Loop

```c
while(1)
```

or

```c
for(;;)
```

---

## 6. Character ASCII Values

```c
char c = 'A';
printf("%d", c);
```

### Output

```
65
```

---

## 7. Convert Lowercase to Uppercase

```c
char c = 'a';
c = c - 32;
```

### Result

```
A
```

---

## 8. Multiple Variable Initialization

```c
int a=1,b=2,c=3;
```

---

## 9. Escape Characters

```
\n  new line
\t  tab
\"  quote
```

### Example

```c
printf("Hello\nWorld");
```

### Output

```
Hello
World
```

---

# ⭐ Key Takeaways

- `return` sends a value back to the caller.
- A `return` statement **immediately ends the function**.
- If a function type is **not `void`**, it must return a value.
- Modifying a variable multiple times in a single statement can cause **undefined behavior**.
- Functions can be **nested**.
- **Ternary operators** make code shorter and cleaner.
