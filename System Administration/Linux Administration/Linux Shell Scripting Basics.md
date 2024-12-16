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
my_variable="Hello, Linux!"
echo $my_variable
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
