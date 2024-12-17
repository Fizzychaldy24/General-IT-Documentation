[System Administration](../README.md)
# Linux Shell Scripting Basics

This guide provides an introduction to shell scripting for **Linux system administrators**. Shell scripting allows you to automate tasks, perform system maintenance, and handle repetitive tasks efficiently. Learning shell scripting is essential for improving your productivity as a system administrator.

## Table of Contents

1. [What is Shell Scripting?](#what-is-shell-scripting)
2. [Getting Started with Shell Scripting](#getting-started-with-shell-scripting)
   - [Creating Your First Script](#creating-your-first-script)
   - [Basic Script Structure](#basic-script-structure)
3. [Essential Shell Scripting Concepts](#essential-shell-scripting-concepts)
   - [Variables and User Input](#variables-and-user-input)
   - [Conditional Statements](#conditional-statements)
   - [Loops](#loops)
   - [Functions](#functions)
4. [Executing Shell Scripts](#executing-shell-scripts)
5. [Debugging and Error Handling](#debugging-and-error-handling)
6. [Best Practices for Shell Scripting](#best-practices-for-shell-scripting)
7. [Conclusion](#conclusion)

## What is Shell Scripting?

**Shell scripting** is a way to automate tasks in the Linux operating system. It involves writing a series of commands in a file that can be executed as a program. These scripts can perform tasks such as file manipulation, user management, and even system configuration.

- **Shell**: The command-line interface that interacts with the kernel of the operating system (e.g., `bash`, `zsh`).
- **Script**: A plain text file that contains a sequence of commands that the shell can execute.

## Getting Started with Shell Scripting

### Creating Your First Script

To create a simple shell script, follow these steps:

1. Open your terminal.
2. Create a new file using a text editor such as `nano` or `vim`:

```bash
nano my_first_script.sh
```

In the file, write the following lines:

```bash
#!/bin/bash
echo "Hello, World!"
```

Save and exit the text editor.

### Basic Script Structure

A typical shell script has the following structure:

1. **Shebang (`#!/bin/bash`)**: This is the first line of the script, indicating the shell that should be used to interpret the script.
2. **Commands**: The script can contain any Linux commands, such as `echo`, `ls`, `cd`, and more.

```bash
#!/bin/bash
# This is a comment
echo "Hello, World!"
```

# Essential Shell Scripting Concepts

## Variables and User Input

Variables allow you to store data to use later in your script. You can also capture user input.

### Defining variables:

```bash
my_variable="Hello, Linux!"  # Define a variable
echo $my_variable  # Display the value of the variable
```
my_variable="Hello, Linux!": This creates a variable named my_variable and assigns it the value "Hello, Linux!".
echo $my_variable: The echo command prints the value of my_variable to the screen. The $ sign before the variable name is used to access the value stored in the variable.

### User Input: Use read to get input from the user.

```bash
echo "Enter your name:"
read name
echo "Hello, $name!"
```
1. `echo "Enter your name:"`  
   Prints a message asking the user to input their name.

2. `read name`  
   This command waits for the user to type something and then assigns the input to the variable `name`.

3. `echo "Hello, $name!"`  
   Prints a personalized greeting using the value stored in the `name` variable.

# Conditional Statements

Conditional statements allow you to perform actions based on specific conditions. They are essential for controlling the flow of your script. The basic syntax for an `if` statement is:

```bash
if [ condition ]; then
   # commands
else
   # other commands
fi
```

### Example:

```bash
echo "Enter a number:"
read number
if [ $number -gt 10 ]; then
    echo "The number is greater than 10."
else
    echo "The number is 10 or less."
fi
```

1. `read number`  
   Reads input from the user and stores it in the variable `number`.

2. `[ $number -gt 10 ]`  
   This is a test condition. It checks if the value of `number` is greater than 10 (`-gt` means "greater than").

   - If the condition is true, the script executes the command:  
     `echo "The number is greater than 10."`
   
   - If the condition is false, the script executes the `else` block, printing:  
     `The number is 10 or less.`

# Loops

Loops allow you to repeat tasks multiple times. The most common loops in shell scripting are the `for` loop and the `while` loop.

### For Loop

The `for` loop is used to iterate over a sequence of values or numbers.

```bash
for i in {1..5}
do
    echo "Number $i"
done

```
1. `for i in {1..5}`  
   This sets up a loop that iterates over the numbers 1 to 5.

2. `do`  
   Marks the beginning of the commands to be executed for each iteration.

3. `echo "Number $i"`  
   Prints the value of `i` during each iteration.

4. `done`  
   Marks the end of the loop.

### While loop:
````bash
count=1
while [ $count -le 5 ]
do
    echo "Count is $count"
    ((count++))
done
````
1. `count=1`  
   Initializes the `count` variable to 1.

2. `while [ $count -le 5 ]`  
   Starts a loop that continues while `count` is less than or equal to 5 (`-le` means "less than or equal to").

3. `echo "Count is $count"`  
   Prints the current value of `count`.

4. `((count++))`  
   Increments the value of `count` by 1 after each iteration.

5. `done`  
   Marks the end of the loop.
# Functions

Functions in shell scripts allow you to group commands into reusable blocks.

## Defining a Function:

```bash
my_function() {
    echo "This is a function!"
}
```

### Calling a Function in Shell Scripting

To call a function in shell scripting, you simply write the function's name followed by any required arguments (if any). For example:

```bash
my_function
```

# Executing Shell Scripts

To run a shell script:

1. **Ensure the script has executable permissions:**

```bash
chmod +x my_first_script.sh
```

2. **Execute the script:**

```bash
./my_first_script.sh
```

3. **This should output:**

```bash
Hello, World!
```

# Debugging and Error Handling

Errors may occur while working with shell scripts. Here’s how to handle them effectively:

1. **Debugging:**  
Use the `-x` option to debug a script and view each command as it is executed:

```bash
bash -x my_first_script.sh  # Debugs the script and shows each command as it runs
```
2. **Exit Status:**
Every command in Linux returns an `exit` status (`0` for success, `non-zero` for failure). You can check the exit status with:

```bash
echo $?
```

3. **Error Handling:**
Use `exit` to terminate a script or return a specific status code.

```bash
if [ ! -f "myfile.txt" ]; then
    echo "File not found!"
    exit 1
fi
```

# Best Practices for Shell Scripting

1. **Comment Your Code:**  
   Use comments (`#`) to explain complex or important parts of your script.

2. **Use Descriptive Variable Names:**  
   Clear variable names enhance readability and maintainability.

3. **Test Your Scripts Thoroughly:**  
   Before deploying a script on a production system, test it in a safe environment to prevent accidental system damage.

4. **Use `set -e`:**  
   Add `set -e` at the beginning of your script to ensure it stops if any command fails.

5. **Break Down Large Scripts:**  
   Use functions to divide your script into smaller, reusable blocks of code.

6. **Handle Errors Gracefully:**  
   Always check for potential errors and handle them appropriately, providing useful messages when necessary.

# Conclusion

Learning shell scripting is an invaluable skill for Linux system administrators. It allows you to automate routine tasks, streamline system maintenance, and improve efficiency. By mastering basic concepts like variables, conditionals, loops, and functions, you can create powerful scripts that simplify workflows and save time.

As you gain experience, explore more advanced topics like arrays, input/output redirection, and file handling. With practice, you'll become proficient in writing scripts that make managing Linux systems more efficient and less error-prone.
