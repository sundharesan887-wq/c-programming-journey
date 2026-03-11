# 📘 C Programming — File Handling (Complete Guide)

File handling allows C programs to **read and write data to files stored on disk**.

Files allow programs to **store data permanently**.

Example file:

```
Alice 90
Bob 85
```

---

# 1️⃣ File Pointer

A **file pointer** is used to access files.

## Syntax

```c
FILE *fp;
```

Example:

```c
FILE *fp;
```

Think of it like:

```
fp → pointer to file
```

---

# 2️⃣ Opening a File

## Syntax

```c
fopen("filename","mode");
```

## Example

```c
fp = fopen("data.txt","r");
```

---

# 3️⃣ File Modes

| Mode | Meaning |
|-----|--------|
| r | read file |
| w | write file (overwrite) |
| a | append to file |
| r+ | read + write |
| w+ | read + write (overwrite) |
| a+ | read + append |
| rb | read binary |
| wb | write binary |

---

# 4️⃣ Closing a File

## Syntax

```c
fclose(fp);
```

## Example

```c
fclose(fp);
```

Always **close files after use**.

---

# 5️⃣ Writing Text — `fprintf`

## Syntax

```c
fprintf(file_pointer,"format",values);
```

## Example

```c
fprintf(fp,"Hello World");
```

File becomes:

```
Hello World
```

---

# 6️⃣ Reading Text — `fscanf`

## Syntax

```c
fscanf(file_pointer,"format",&variable);
```

## Example

```c
char ch;

fscanf(fp,"%c",&ch);
```

### Why `&`?

Because `fscanf` needs the **memory address to store the data**.

---

# 7️⃣ Read a Line — `fgets`

## Syntax

```c
fgets(string,size,file_pointer);
```

## Example

```c
char line[100];

fgets(line,100,fp);
```

Reads **one line from the file**.

---

# 8️⃣ Write String — `fputs`

## Syntax

```c
fputs(string,file_pointer);
```

## Example

```c
fputs("Hello",fp);
```

---

# 9️⃣ Read Character — `fgetc`

## Syntax

```c
char ch = fgetc(file_pointer);
```

## Example

```c
char ch;
ch = fgetc(fp);
```

Reads **one character**.

---

# 🔟 Write Character — `fputc`

## Syntax

```c
fputc(character,file_pointer);
```

## Example

```c
fputc('A',fp);
```

Writes **one character**.

---

# 1️⃣1️⃣ Read Binary Data — `fread`

## Syntax

```c
fread(pointer,size,count,file_pointer);
```

## Example

```c
int x;

fread(&x,sizeof(int),1,fp);
```

Meaning:

```
Read 1 integer from file
Store it in x
```

### Explanation

| Part | Meaning |
|-----|--------|
| `&x` | address to store data |
| `sizeof(int)` | size of integer |
| `1` | number of integers |
| `fp` | file pointer |

---

# 1️⃣2️⃣ Write Binary Data — `fwrite`

## Syntax

```c
fwrite(pointer,size,count,file_pointer);
```

## Example

```c
int x = 100;

fwrite(&x,sizeof(int),1,fp);
```

Writes **binary data to file**.

---

# 1️⃣3️⃣ File Copy Program

```c
FILE *fp1,*fp2;
char ch;

fp1 = fopen("a.txt","r");
fp2 = fopen("b.txt","w");

while((ch = fgetc(fp1)) != EOF)
{
    fputc(ch,fp2);
}

fclose(fp1);
fclose(fp2);
```

Copies content of:

```
a.txt → b.txt
```

---

# 1️⃣4️⃣ Counting Characters in File

```c
FILE *fp;
char ch;
int count=0;

fp = fopen("data.txt","r");

while((ch = fgetc(fp)) != EOF)
{
    count++;
}

printf("%d",count);

fclose(fp);
```

Counts **characters in the file**.

---

# 1️⃣5️⃣ Append Mode

Append means:

```
Add new data at end of file
```

Example:

Before:

```
Hello
```

After append:

```
Hello
World
```

Example code:

```c
fp = fopen("data.txt","a");

fprintf(fp,"World");
```

---

# 1️⃣6️⃣ Binary vs Text Files

| Type | Description |
|-----|-------------|
| Text File | human readable |
| Binary File | computer readable |

Example text:

```
Hello
```

Example binary:

```
01001000
```

---

# 🧠 Simple File Handling Flow

```
1 Open file
2 Read / Write
3 Close file
```

Example:

```c
fp = fopen("data.txt","r");

fgets(line,100,fp);

fclose(fp);
```

---

# ⭐ Most Important File Functions

| Function | Purpose |
|---------|---------|
| `fopen()` | open file |
| `fclose()` | close file |
| `fprintf()` | write formatted text |
| `fscanf()` | read formatted text |
| `fgetc()` | read character |
| `fputc()` | write character |
| `fgets()` | read line |
| `fputs()` | write string |
| `fread()` | read binary data |
| `fwrite()` | write binary data |

---

# 🚀 Real Uses of File Handling

File handling is used in:

- databases
- saving game progress
- student record systems
- log files
- operating systems
