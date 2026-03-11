# 📘 C Programming – Dynamic Memory Allocation

Dynamic Memory Allocation (DMA) allows a C program to **allocate memory during runtime** (while the program is running) instead of before execution.

This is useful when the **size of data is not known beforehand**.

Example situation:

```
How many numbers do you want to store?
```

User input:

```
7
```

Now the program must create memory for **7 numbers dynamically**.

---

# 🧠 Memory Areas in a C Program

```
+-------------------+
| Code Segment      | → Program instructions
+-------------------+
| Data Segment      | → Global variables
+-------------------+
| Stack             | → Local variables
+-------------------+
| Heap              | → Dynamic memory
+-------------------+
```

Dynamic memory functions allocate memory from the **Heap**.

---

# 📦 Dynamic Memory Functions

Defined in:

```c
#include <stdlib.h>
```

| Function | Expansion | Purpose |
|---------|-----------|---------|
| malloc() | Memory Allocation | Allocates memory |
| calloc() | Contiguous Allocation | Allocates memory and sets to 0 |
| realloc() | Reallocation | Resizes allocated memory |
| free() | Free Memory | Releases memory |

---

# 1️⃣ malloc() – Memory Allocation

Allocates a block of memory.

## Syntax

```c
ptr = (type*) malloc(size);
```

## Example

```c
int *arr;
arr = (int*) malloc(5 * sizeof(int));
```

### Explanation

Create memory for **5 integers**.

Memory:

```
[ ][ ][ ][ ][ ]
```

Values initially contain **garbage values**.

---

# 2️⃣ calloc() – Contiguous Allocation

Allocates memory and **initializes it with zero**.

## Syntax

```c
ptr = (type*) calloc(n, size);
```

## Example

```c
int *arr;
arr = (int*) calloc(5, sizeof(int));
```

Memory:

```
[0][0][0][0][0]
```

---

# 3️⃣ realloc() – Reallocation

Resizes previously allocated memory.

## Syntax

```c
ptr = realloc(ptr, new_size);
```

## Example

```c
arr = realloc(arr, 10 * sizeof(int));
```

Memory before:

```
[10][20][30][40][50]
```

Memory after resizing:

```
[10][20][30][40][50][ ][ ][ ][ ][ ]
```

---

# 4️⃣ free() – Release Memory

Releases dynamically allocated memory.

## Syntax

```c
free(ptr);
```

## Example

```c
free(arr);
```

If memory is not freed, it causes a **memory leak**.

---

# 🧩 Practice Exercises

## 1️⃣ Dynamic Array

### Goal

Create an array dynamically based on **user input size**.

### Program

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *arr;
    int n;

    printf("Enter size: ");
    scanf("%d",&n);

    arr = (int*) malloc(n * sizeof(int));

    for(int i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }

    for(int i=0;i<n;i++)
    {
        printf("%d ",arr[i]);
    }

    free(arr);

    return 0;
}
```

### Explanation

User decides array size:

```
Enter size → 5
```

Memory created dynamically:

```
[ ][ ][ ][ ][ ]
```

User fills values:

```
[10][20][30][40][50]
```

---

# 2️⃣ Sum of Elements

## Goal

Allocate memory for **N numbers** and calculate their sum.

## Program

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *arr;
    int n, sum = 0;

    printf("Enter number of elements: ");
    scanf("%d",&n);

    arr = (int*) malloc(n * sizeof(int));

    for(int i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
        sum += arr[i];
    }

    printf("Sum = %d",sum);

    free(arr);

    return 0;
}
```

### Explanation

User input:

```
1 2 3 4 5
```

Calculation:

```
1+2+3+4+5 = 15
```

Output:

```
Sum = 15
```

---

# 3️⃣ Resize Array

## Goal

Create memory for **3 numbers**, then expand it to **6 numbers using realloc()**.

## Program

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *arr;

    arr = (int*) malloc(3 * sizeof(int));

    printf("Enter 3 numbers:\n");

    for(int i=0;i<3;i++)
    {
        scanf("%d",&arr[i]);
    }

    arr = realloc(arr,6 * sizeof(int));

    printf("Enter 3 more numbers:\n");

    for(int i=3;i<6;i++)
    {
        scanf("%d",&arr[i]);
    }

    printf("Numbers are:\n");

    for(int i=0;i<6;i++)
    {
        printf("%d ",arr[i]);
    }

    free(arr);

    return 0;
}
```

### Explanation

Initial memory:

```
[ ][ ][ ]
```

After input:

```
[10][20][30]
```

After realloc():

```
[10][20][30][ ][ ][ ]
```

Final array:

```
[10][20][30][40][50][60]
```

---

# 🔄 Dynamic Memory Workflow

Typical steps:

```
1 Allocate memory → malloc / calloc
2 Use memory
3 Resize memory → realloc (optional)
4 Release memory → free
```

Workflow diagram:

```
malloc → use → realloc → free
```

---

# ⚖️ malloc vs calloc

| Feature | malloc | calloc |
|--------|--------|--------|
| Arguments | 1 | 2 |
| Initialization | Garbage values | Zero values |
| Speed | Slightly faster | Slightly slower |

Example:

```c
malloc(5 * sizeof(int));
calloc(5, sizeof(int));
```

---

# ⭐ 10 Important Things About Dynamic Memory

1️⃣ Dynamic memory is allocated from the **heap**.  
2️⃣ `malloc()` allocates memory but does **not initialize values**.  
3️⃣ `calloc()` allocates memory and sets values to **zero**.  
4️⃣ `realloc()` resizes existing memory blocks.  
5️⃣ `free()` releases allocated memory.  
6️⃣ Memory allocated dynamically **stays until explicitly freed**.  
7️⃣ Not freeing memory causes **memory leaks**.  
8️⃣ `sizeof()` helps allocate correct memory size.

Example:

```c
malloc(n * sizeof(int));
```

9️⃣ Dynamic arrays allow **user-defined sizes during runtime**.  
🔟 Always check allocation success:

```c
if(ptr == NULL)
{
    printf("Memory allocation failed");
}
```

---

# 🧠 Simple Analogy

Dynamic memory is like **renting storage boxes**.

```
malloc  → rent boxes
realloc → increase/decrease boxes
free    → return boxes
```

---

# 📌 Key Rule

Always release memory after use:

```c
free(ptr);
```

Otherwise memory stays **occupied**.
