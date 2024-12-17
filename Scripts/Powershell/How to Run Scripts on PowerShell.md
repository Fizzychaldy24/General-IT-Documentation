[General IT Documentation](../README.md)
# How to Create and Run a PowerShell Script

This guide will show you how to create and run a basic PowerShell script on a Windows system.

---

## Table of Contents

1. [Create a New PowerShell Script](#1-create-a-new-powershell-script)
   - [Step 1: Open PowerShell](#step-1-open-powershell)
   - [Step 2: Create a New File](#step-2-create-a-new-file)
   - [Step 3: Write Your Script](#step-3-write-your-script)
   - [Step 4: Save the Script](#step-4-save-the-script)
2. [Make the Script Executable](#2-make-the-script-executable)
3. [Run the Script](#3-run-the-script)
4. [Run the Script with PowerShell](#4-run-the-script-with-powershell)
5. [Debugging and Testing the Script](#5-debugging-and-testing-the-script)
6. [Additional Tips](#6-additional-tips)
   - [Comments](#comments)
   - [Variables](#variables)
   - [Loops and Conditions](#loops-and-conditions)
7. [Conclusion](#conclusion)

---

## 1. **Create a New PowerShell Script**

To create a PowerShell script, follow these steps:

### Step 1: Open PowerShell
Press `Win + X`, then choose `Windows PowerShell` or `Windows PowerShell (Admin)` from the menu.

### Step 2: Create a New File
You can create a new script file using any text editor. For example, using `Notepad`:

1. Open Notepad (or another text editor).
2. Save the file with a `.ps1` extension (e.g., `myscript.ps1`).

Alternatively, you can use the `New-Item` command in PowerShell to create the file directly:

```powershell
New-Item -Path "C:\path\to\your\folder" -Name "myscript.ps1" -ItemType File
```

## Step 3: Write Your Script
Below is an example of a simple PowerShell script that prints "Hello, World!" to the console:
```bash
Write-Host "Hello, World!"
```

## Step 4: Save the Script

Save your script by clicking "File" → "Save" in your text editor.

----

## 2. Make the Script Executable

PowerShell scripts need to be allowed to run. By default, PowerShell restricts script execution for security reasons. To allow the execution of scripts, follow these steps:

1. Open PowerShell as Administrator.
2. Run the following command to change the execution policy:
```bash
Set-ExecutionPolicy RemoteSigned
```
This allows locally created scripts to run while requiring downloaded scripts to be signed by a trusted publisher.

> **Note**: You can also use `Unrestricted` if you want to allow all scripts to run without any restrictions.
----

## 3. Run the Script

To run the script, navigate to the folder where your script is located and execute it using the following command:
```bash
.\myscript.ps1
```
The `.\` is necessary if you are running the script from the current directory.

----

## 4. Run the Script with PowerShell

Alternatively, you can also run the script directly from PowerShell by specifying the full path to the script file:
```bash
powershell.exe -ExecutionPolicy RemoteSigned -File C:\path\to\your\script\myscript.ps1
```
This ensures the script runs even if you don't navigate to the folder.

---

## 5. Debugging and Testing the Script
If you encounter issues with your script, you can enable script debugging by using `Set-PSDebug`:
```bash
Set-PSDebug -Trace 1
```
This will show a step-by-step trace of the script's execution, which is useful for debugging.

To disable debugging, use:
```bash
Set-PSDebug -Off
```
---

## 6. Additional Tips

- **Comments**: You can add comments to your script using the `#` symbol. Comments are ignored by PowerShell and are helpful for explaining your code.
```bash
# This is a comment
Write-Host "This will be printed"
```
- **Variables**: You can define variables to store values.
```bash
$name = "Alice"
Write-Host "Hello, $name!"
```
- **Loops and Conditions**: PowerShell supports loops and conditional statements.
```bash
# For Loop Example
for ($i = 1; $i -le 5; $i++) {
    Write-Host "Number: $i"
}

# If-Else Example
if ($name -eq "Alice") {
    Write-Host "Welcome, Alice!"
} else {
    Write-Host "You're not Alice!"
}
```
---
## Conclusion
You’ve now learned how to create and run a basic PowerShell script! PowerShell scripts are powerful tools for automating tasks, managing system configurations, and more. Experiment with different commands and logic to expand your PowerShell scripting skills.
### Key Points:
- **Creating a Script**: Using Notepad or PowerShell to create a `.ps1` file.
- **Making it Executable**: Changing the execution policy with `Set-ExecutionPolicy`.
- **Running the Script**: Executing the script with `.\myscript.ps1` or `powershell.exe`.
- **Debugging**: Using `Set-PSDebug` to trace the script's execution.
- **Scripting Basics**: Examples of comments, variables, loops, and conditions.
### Key Sections:
1. **Table of Contents**: An easy-to-navigate index for the document.
2. **Creating a Script**: Instructions on creating a PowerShell script, writing it, and saving it.
3. **Making the Script Executable**: Instructions to set the execution policy so you can run scripts.
4. **Running the Script**: Detailed instructions for executing the script.
5. **Debugging**: How to enable debugging in PowerShell to help with testing and troubleshooting.
6. **Additional Tips**: Comments, variables, and examples of loops and conditions in PowerShell.
This should help guide users through creating and running PowerShell scripts in a clear, organized way!
