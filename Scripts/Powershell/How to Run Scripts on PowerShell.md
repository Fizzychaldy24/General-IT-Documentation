# How to Create and Run a PowerShell Script

This guide will show you how to create and run a basic PowerShell script on a Windows system.

---

## Table of Contents

1. [Create a New PowerShell Script](#1-create-a-new-powershell-script)
   - [Open PowerShell](#open-powershell)
   - [Create a New File](#create-a-new-file)
   - [Write Your Script](#write-your-script)
   - [Save the Script](#save-the-script)
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
New-Item -Path "C:\path\to\your\folder" -Name "myscript.ps1
