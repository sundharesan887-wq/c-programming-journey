# ⚙️ How a C Program Actually Runs

When you write a C program, the computer **cannot run it directly**.

The file you write is called **source code**.

# Example:

  #include <stdio.h>

  int main() {
  
  printf("Welcome to the C Programming Journey!\n");
  
  return 0;
   
  }

This file usually ends with:

**.c**

# Example:

**first-program.c**

But computers do not understand C language.

They only understand machine code.

So the program must go through a process called compilation.

# 🧠 The Journey of a C Program

When you run a program, it goes through several steps.

***Source Code → Compiler → Machine Code → Program Runs***

Let's understand each step.

# 1️⃣ Source Code

Source code is the program you write.

# Example file:

  first-program.c

**It contains instructions written in C.**

Humans can read this easily.

But computers cannot execute it yet.

# 2️⃣ The Compiler

**A compiler is a program that translates C code into machine code.**

Common C compilers:

GCC

Clang

MSVC

The compiler reads your .c file and converts it into something the computer understands.

# Example command:

   gcc first-program.c

# 3️⃣ Machine Code

After compilation, the compiler produces a new file.

# Example:

   a.exe

   (or)

   a.out

This file contains machine instructions.

# Example machine code might look like:

**101010101000101010**

Only the CPU understands this.

# 4️⃣ Running the Program

Now the operating system loads the compiled program into memory.

Then the CPU starts executing instructions.

The CPU reads instructions one by one.

# Example flow:

Start program
Enter main()
Execute printf()
Print text
Return 0
End program

# 📦 Visual Summary

first-program.c

        
  ↓
  
Compiler (GCC)

  ↓
  
Executable file (a.exe)

  ↓
  
Program runs

  ↓
  
Output appears on screen

# 🧠 Compiler vs Interpreter

There are two types of programming language translators.

# Compiler

**A compiler translates the entire program into machine code before running it.**

**Examples of compiled languages:**

C

C++

Rust

Go

# How it works
   Source Code → Compiler → Machine Code → Run Program

The compiler converts the whole program into an executable file.

Once compiled, the program runs very fast.

# Interpreter

**An interpreter executes the program line by line.**

**Examples of interpreted languages:**

Python

JavaScript

Ruby

# How it works
   Source Code → Interpreter → Execute Line by Line

The interpreter reads one instruction at a time and executes it immediately.

## 📊 Compiler vs Interpreter

| Feature | Compiler | Interpreter |
|--------|--------|-------------|
| Translation | Translates the entire program at once | Translates and executes line by line |
| Execution Speed | Faster (after compilation) | Slower |
| Output | Produces an executable file | No executable file |
| Error Detection | Shows errors after compilation | Shows errors one line at a time |
| Examples | C, C++, Rust, Go | Python, JavaScript, Ruby |

**C uses a compiler, which is why C programs are extremely fast.**

# ⚠️ Compile vs Run

Many beginners confuse these two steps.

**Compile**

   gcc first-program.c

**Run**

   a.exe

Compilation converts the program into machine code.

Running executes the compiled program.

# 🧩 Mini Challenges

Try the following:

1️⃣ Write your program using Notepad

2️⃣ Save it as

  my-program.c

3️⃣ Compile it

   gcc my-program.c

4️⃣ Run it

  my-program.exe

5️⃣ Modify the message and run it again.

# 📦Sample Program

# 1️⃣ Writing the Program

First we write the program.

You can even write a C program using Notepad.

Example program:

#include <stdio.h>

int main() {

  printf("Welcome to the C Programming Journey!\n");

  return 0;
}

# 2️⃣ Saving the File
Save the file with the .c extension.

Example:

 **first-program.c**

The .c extension tells the compiler that this file contains C source code.

# 3️⃣ Opening Command Prompt

To compile the program, open Command Prompt (CMD).

Navigate to the folder containing your program.

Example command:

  cd Desktop

  or

  cd c-programming-journey
  
# 4️⃣ Compiling the Program

To compile the program we use the GCC compiler.

**Command:**

   ***gcc first-program.c***

# What happens here?

GCC reads your C code

It translates the code into machine instructions

It creates an executable file

# 5️⃣ Generated Executable File

After compilation, a new file appears.

**Example:**

  a.exe

  (or sometimes)

  a.out

This file contains machine code that the CPU can execute.

# 6️⃣ Running the Program

To run the program, type:

  a

  or

  a.exe

Then press Enter.

The program executes and prints the output.

# 🧪 Example Output

**Welcome to the C Programming Journey!**

# 🚀 What Comes Next

Now that we understand:

**source code**

**compilers**

**interpreters**

**how programs run**

We are ready to explore the structure of a C program.

# Next chapter:

***Structure of a C Program***

In that chapter we will analyze:

**header files**

**main function**

**statements**

**program execution flow**
