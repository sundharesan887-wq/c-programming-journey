# 📂 File Handling in C

So far our programs stored data **only in memory**.

Example:

```c
int marks = 90;
```

If the program stops running, the data is **lost**.

To store data permanently, we use **files**.

Files allow programs to:

- save data
- read stored data
- update information
- process large datasets

---

# 🧠 What is a File?

A **file** is a collection of data stored on a storage device such as:

- hard disk
- SSD
- USB drive

Example files:

```
students.txt
data.csv
notes.txt
```

Programs can **read and write data** to these files.

---

# 📌 File Pointer

In C, files are handled using **file pointers**.

A file pointer is declared using the `FILE` type.

Example:

```c
FILE *fp;
```

Here:

```
FILE → structure defined in stdio.h
fp   → pointer to file
```

---

# 📚 Opening a File

Files are opened using:

```
fopen()
```

## Syntax

```c
FILE *fp = fopen("filename", "mode");
```

## Example

```c
FILE *fp = fopen("data.txt", "w");
```

---

# 📊 File Opening Modes

| Mode | Purpose |
|-----|--------|
| `"r"` | Read file |
| `"w"` | Write file (creates new file) |
| `"a"` | Append to file |
| `"r+"` | Read and write |
| `"w+"` | Read and write (overwrite file) |

---

# 📝 Writing to a File

## Example Program

```c
#include <stdio.h>

int main()
{
    FILE *fp;

    fp = fopen("data.txt", "w");

    fprintf(fp, "Hello File\n");

    fclose(fp);

    return 0;
}
```

## What Happens

Step-by-step:

1. `fopen()` creates `data.txt`
2. `fprintf()` writes text into the file
3. `fclose()` closes the file

File content becomes:

```
Hello File
```

---

# 📖 Reading from a File

## Example

```c
#include <stdio.h>

int main()
{
    FILE *fp;
    char text[100];

    fp = fopen("data.txt", "r");

    fscanf(fp, "%s", text);

    printf("%s\n", text);

    fclose(fp);

    return 0;
}
```

## Output

```
Hello
```

Note:

```
%s reads until a space.
```

---

# 📄 Reading Full Lines

To read complete lines we use:

```
fgets()
```

## Example

```c
#include <stdio.h>

int main()
{
    FILE *fp;
    char line[100];

    fp = fopen("data.txt", "r");

    fgets(line, sizeof(line), fp);

    printf("%s", line);

    fclose(fp);

    return 0;
}
```

---

# ➕ Appending to a File

Append mode adds data **without deleting existing content**.

## Example

```c
#include <stdio.h>

int main()
{
    FILE *fp;

    fp = fopen("data.txt", "a");

    fprintf(fp, "New Line Added\n");

    fclose(fp);

    return 0;
}
```

File becomes:

```
Hello File
New Line Added
```

---

# ⚠ Always Close Files

Always close files using:

```c
fclose(fp);
```

Reason:

- releases memory
- saves changes
- prevents file corruption

---

# 📊 File Operation Summary

| Function | Purpose |
|--------|---------|
| `fopen()` | open file |
| `fprintf()` | write formatted output |
| `fscanf()` | read formatted input |
| `fgets()` | read line |
| `fclose()` | close file |

---

# ⚠ Common Beginner Mistakes

## File Not Opened

Always check if the file opened successfully.

Example:

```c
if(fp == NULL)
{
    printf("File not found\n");
}
```

---

## Forgetting `fclose`

Leaving files open can cause **data loss or corruption**.

---

# 🧩 Practice Exercises

## 1️⃣ Write to File

Create a program that writes:

```
Learning C File Handling
```

to a file.

---

## 2️⃣ Read File

Create a program that **reads a file and prints its content**.

---

## 3️⃣ Student Record

Write student name and marks to a file.

Example file:

```
Alice 90
Bob 85
```

---

# 🧠 Super Challenge

Predict the output.

```c
#include <stdio.h>

int main()
{
    FILE *fp;

    fp = fopen("test.txt", "w");

    fprintf(fp, "ABC");

    fclose(fp);

    fp = fopen("test.txt", "r");

    char ch;

    fscanf(fp, "%c", &ch);

    printf("%c\n", ch);

    fclose(fp);

    return 0;
}
```

---

# Try Before Looking

Think about what gets written and read.

---

# ✅ Solution

File content after writing:

```
ABC
```

Reading first character:

```
A
```

---

# Final Output

```
A
```

---

# 🧠 Key Takeaways

You learned:

- file pointers
- file opening modes
- reading files
- writing files
- appending data
- closing files

File handling allows programs to **store and process persistent data**.
