# Writing Our First C Program

Now we will write our first C program.

Here is the complete program:

#include <stdio.h>

  int main() {
   
    printf("Welcome to the C Programming Journey!\n");
    printf("Let's learn how computers think.\n");
    
  return 0;
    
  }
    
### Line-by-Line Explanation

Let's break the program down.

# 1️⃣ #include <stdio.h>

# What it does

This line tells the compiler:

**Include the Standard Input Output library.**

This library allows us to use functions like:

 printf() → print text

 scanf() → read user input

Without this line, the compiler would not recognize printf().

# What happens if we remove it?

The program will produce an error because printf() would be undefined.

# 2️⃣ int main()

# What it does

This defines the main function.

Every C program starts execution from main().

You can think of it as the entry point of the program.

The computer begins reading instructions here.

# Why int?

int means the function returns an integer value to the operating system.

# 3️⃣ { }

{
}

These curly braces define a **block of code.**

Everything inside the braces belongs to the main() function.

# 4️⃣ printf()

printf("Welcome to the C Programming Journey!\n");

# What it does

printf() prints text to the screen.

The text inside quotes is called a string.

# What is \n ?

\n means new line.

It moves the cursor to the next line.

Example output:

Welcome to the C Programming Journey!

Let's learn how computers think.

# 5️⃣ Semicolon ;

**Every statement in C ends with a semicolon.**

# Example:

printf("Hello");

Without the semicolon, the compiler will show an error.

# 6️⃣ return 0;

# What it does

This tells the operating system:

  The program finished successfully.

The number *0* usually means success.

# Program Execution Flow

When this program runs, the computer executes steps in this order:

1 Start program

2 Enter main()

3 Execute first printf

4 Execute second printf

5 Return 0

6 End program

# Output of the Program
 Welcome to the C Programming Journey!
 
 Let's learn how computers think.
 
# Mini Challenges

Try modifying the program.

   1 Print your name
   
   2 Print your favorite quote
   
   3 Print three lines instead of two

# Example challenge:

    printf("I am learning C programming.\n");
   
# Key Takeaways

From this simple program we learned:

   **How a C program starts**

   **How to print text**
  
   **Why semicolons matter**
  
   **How program execution flows**
