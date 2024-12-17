# How to Create and Run a Linux Bash Script

This guide will show you how to create and run a basic Bash script on a Linux system.

---

## Table of Contents
1. [Create a New Bash Script](#1-create-a-new-bash-script)
   - [Open a Terminal](#step-1-open-a-terminal)
   - [Create a New File](#step-2-create-a-new-file)
2. [Add the Shebang](#step-3-add-the-shebang)
3. [Write Your Script](#step-4-write-your-script)
4. [Save the Script](#step-5-save-the-script)
5. [Make the Script Executable](#2-make-the-script-executable)
6. [Run the Script](#3-run-the-script)
7. [Alternative - Run the Script with Bash](#4-alternative---run-the-script-with-bash)
8. [Debugging and Testing the Script](#5-debugging-and-testing-the-script)
9. [Additional Tips](#6-additional-tips)
10. [Conclusion](#conclusion)
    - [Key Points](#key-points)

---

## 1. **Create a New Bash Script**

To create a bash script, follow these steps:

### Step 1: Open a Terminal
Press `Ctrl + Alt + T` to open a terminal on your Linux system.

### Step 2: Create a New File
You can create a new script file using any text editor. For example, using `nano`:

```bash
nano myscript.sh
```
This will open the nano text editor where you can write your script. Replace `myscript.sh` with the desired name of your script.

## Step 3: Add the Shebang

At the top of your script, you need to include the shebang line (`#!/bin/bash`) to indicate that the script should be executed using Bash:
```bash
#!/bin/bash
```
## Step 4: Write Your Script

Below the shebang, you can start writing your script. For example:
````bash
#!/bin/bash

echo "Hello, World!"
````

This script simply prints "Hello, World!" to the terminal.

## Step 5: Save the Script

If you're using nano, press `Ctrl + X` to exit, then press `Y` to confirm saving, and press `Enter` to save the file.

## 2. Make the Script Executable

Before running the script, you need to make it executable. In the terminal, run the following command:
```bash
chmod +x myscript.sh
```
This command grants execution permission to the script file.

## 3. Run the Script
To run the script, use the following command:
```bash
./myscript.sh
```
This will execute the script, and you should see the output (e.g., "Hello, World!") printed in the terminal.

## 4. Alternative - Run the Script with Bash
You can also run the script without making it executable by explicitly calling bash:
```bash
bash myscript.sh
```
## 5. Debugging and Testing the Script
If you encounter issues, you can run the script with the `-x` option to see what is happening at each step:
```bash
bash -x myscript.sh
```
This will display each command as it is executed, which is useful for debugging.

## 6. Additional Tips

- **Comments**: You can add comments in your script using the `#` symbol. Comments are ignored by the Bash interpreter and are helpful for explaining the code.
```bash
# This is a comment
echo "This will be printed"
```
- **Variables**: You can define variables to store values in your script.
```bash
#!/bin/bash
name="Alice"
echo "Hello, $name!"
```
- **Loops and Conditions**: Bash scripts support loops and conditional statements.
```bash
#!/bin/bash
for i in {1..5}
do
  echo "Number: $i"
done
````
## Conclusion

You’ve now learned how to create and run a basic Linux bash script! Scripts can be used to automate tasks, manage system configurations, and much more. Experiment with different commands and logic to expand your Bash scripting skills.

---

### Key Points:
1. **Creating a Script**: Using `nano` to create a `.sh` file with a shebang (`#!/bin/bash`).
2. **Making it Executable**: Using `chmod +x` to give the script execution permission.
3. **Running the Script**: Executing the script with `./myscript.sh` or `bash myscript.sh`.
4. **Debugging**: Using `bash -x` to debug the script.
5. **Scripting Basics**: Examples of adding comments, variables, and loops.
