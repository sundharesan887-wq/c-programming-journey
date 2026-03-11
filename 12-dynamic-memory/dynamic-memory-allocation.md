# 🧠 Dynamic Memory Allocation in C

So far we created variables and arrays like this:

```c
int x;
int arr[10];
```

Here, memory size is decided during **compile time**.

But sometimes we don't know how much memory we need until the program runs.

Example:

- number of students  
- number of records  
- user input size  

For such cases we use **Dynamic Memory Allocation (DMA)**.

---

# 📦 Stack vs Heap Memory

Memory in C is mainly divided into two areas.

| Memory Type | Description |
|-------------|-------------|
| Stack | Used for local variables |
| Heap | Used for dynamic memory allocation |

## Stack Memory

Example:

```c
int x = 10;
```

Memory is automatically:

- allocated  
- managed  
- released  

When the function ends.

## Heap Memory

Heap memory is **allocated manually by the programmer**.

Example functions:

```
malloc()
calloc()
realloc()
free()
```

These functions are defined in:

```c
#include <stdlib.h>
```

---

# 📌 Why Dynamic Memory?

Example problem:

```c
int arr[100];
```

But what if the user only needs **10 elements**?

Then **90 elements are wasted memory**.

Dynamic allocation solves this.

---

# 📚 Dynamic Memory Functions

| Function | Purpose |
|----------|---------|
| malloc() | allocate memory |
| calloc() | allocate and initialize memory |
| realloc() | resize memory |
| free() | release memory |

---

# 1️⃣ malloc()

`malloc()` allocates memory during runtime.

## Syntax

```c
pointer = (type*) malloc(size);
```

## Example

```c
int *ptr;

ptr = (int*) malloc(5 * sizeof(int));
```

Meaning:

```
Allocate memory for 5 integers
```

---

## Example Program

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) malloc(3 * sizeof(int));

    ptr[0] = 10;
    ptr[1] = 20;
    ptr[2] = 30;

    for(int i = 0; i < 3; i++)
    {
        printf("%d\n", ptr[i]);
    }

    free(ptr);

    return 0;
}
```

## Output

```
10
20
30
```

---

## Memory Representation

```
ptr → 1000
```

| Address | Value |
|--------|------|
| 1000 | 10 |
| 1004 | 20 |
| 1008 | 30 |

Memory is allocated from the **heap**.

---

# 2️⃣ calloc()

`calloc()` allocates memory and **initializes it to zero**.

## Syntax

```c
calloc(number_of_elements, size_of_element)
```

## Example

```c
int *ptr;

ptr = (int*) calloc(5, sizeof(int));
```

This creates an array of **5 integers initialized to 0**.

---

## Example Program

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) calloc(4, sizeof(int));

    for(int i = 0; i < 4; i++)
    {
        printf("%d\n", ptr[i]);
    }

    free(ptr);

    return 0;
}
```

## Output

```
0
0
0
0
```

---

# 3️⃣ realloc()

`realloc()` changes the **size of allocated memory**.

## Syntax

```c
realloc(pointer, new_size)
```

## Example

```c
ptr = realloc(ptr, 10 * sizeof(int));
```

This resizes the memory block.

---

## Example Program

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) malloc(2 * sizeof(int));

    ptr[0] = 10;
    ptr[1] = 20;

    ptr = realloc(ptr, 4 * sizeof(int));

    ptr[2] = 30;
    ptr[3] = 40;

    for(int i = 0; i < 4; i++)
    {
        printf("%d\n", ptr[i]);
    }

    free(ptr);

    return 0;
}
```

## Output

```
10
20
30
40
```

---

# 4️⃣ free()

`free()` releases dynamically allocated memory.

## Syntax

```c
free(pointer);
```

## Example

```c
free(ptr);
```

This prevents **memory leaks**.

---

# ⚠ Memory Leak

A **memory leak** occurs when allocated memory is **never freed**.

Example mistake:

```c
int *ptr = malloc(10 * sizeof(int));
```

If `free(ptr)` is not called:

```
Memory remains allocated forever
```

---

# 📊 malloc vs calloc

| Feature | malloc | calloc |
|--------|--------|--------|
| Initialization | Not initialized | Initialized to zero |
| Parameters | One parameter | Two parameters |
| Speed | Slightly faster | Slightly slower |

---

# ⚠ Common Beginner Mistakes

## Forgetting `free()`

Always release memory.

---

## Using Pointer After `free()`

Wrong:

```c
free(ptr);
ptr[0] = 10;
```

This causes **undefined behavior**.

---

## Not Checking malloc Result

Example safe version:

```c
if(ptr == NULL)
{
    printf("Memory allocation failed");
}
```

---

# 🧩 Practice Exercises

## 1️⃣ Dynamic Array

Create an array dynamically based on **user input size**.

---

## 2️⃣ Sum of Elements

Allocate memory for **N numbers** and calculate the **sum**.

---

## 3️⃣ Resize Array

Allocate memory for **3 numbers** and later expand it to **6 using `realloc()`**.

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) calloc(3, sizeof(int));

    ptr[1] = 5;

    printf("%d\n", ptr[0]);
    printf("%d\n", ptr[1]);
    printf("%d\n", ptr[2]);

    free(ptr);

    return 0;
}
```

---

# Try Before Looking

Think about how `calloc()` initializes memory.

---

# ✅ Solution

`calloc()` initializes all elements to **0**.

Memory:

```
0 0 0
```

Then:

```
ptr[1] = 5
```

Memory becomes:

```
0 5 0
```

---

# Final Output

```
0
5
0
```

---

# 🧠 Key Takeaways

You learned:

- heap memory  
- dynamic allocation  
- `malloc()`  
- `calloc()`  
- `realloc()`  
- `free()`  
- memory leaks  

Dynamic memory allocation gives **C programs flexible memory management**.
