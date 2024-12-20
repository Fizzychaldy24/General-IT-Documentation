[General IT Documentation](/README.md)
# Hyper-V VM Creation and Management Guide

## Overview
This guide provides detailed instructions for creating, configuring, and managing virtual machines (VMs) in a Hyper-V environment. Hyper-V, a virtualization technology by Microsoft, allows you to create and manage VMs on physical servers. This documentation will help helpdesk staff perform key tasks such as VM creation, configuration, and management in Hyper-V.

---

## Table of Contents
1. [Installing Hyper-V](#1-installing-hyper-v)
2. [Creating a New VM](#2-creating-a-new-vm)
3. [Configuring VM Resources](#3-configuring-vm-resources)
4. [Managing VMs](#4-managing-vms)

---

## 1. Installing Hyper-V

### Prerequisites
- **Operating System**: Hyper-V can be installed on Windows Server (Standard or Datacenter editions) or Windows 10/11 Pro, Enterprise, or Education.
- **System Requirements**:
  - 64-bit processor with Second Level Address Translation (SLAT)
  - 4 GB or more of RAM (for better performance, 8 GB or more is recommended)
  - Virtualization must be enabled in BIOS/UEFI (usually labeled as Intel VT-x or AMD-V).

### Installation Steps for Windows 10/11 (Professional, Enterprise, Education)

1. **Enable Virtualization in BIOS/UEFI:**
   - Reboot your system and enter BIOS/UEFI (usually by pressing **F2**, **F10**, or **Delete** during startup).
   - Enable **Intel VT-x** or **AMD-V** under the CPU or Advanced settings.
   - Save changes and exit.

2. **Install Hyper-V via Windows Features:**
   - Open **Control Panel** > **Programs** > **Turn Windows features on or off**.
   - In the Windows Features window, check **Hyper-V** (this includes both **Hyper-V Management Tools** and **Hyper-V Platform**).
   - Click **OK** to install the feature.
   - After installation, restart your computer.

3. **Enable Hyper-V using PowerShell (alternative method):**
   - Open **PowerShell** as an administrator.
   - Run the following command to install Hyper-V:
     ```powershell
     dism.exe /Online /Enable-Feature /FeatureName:Microsoft-Hyper-V-All /All /LimitAccess /Restart
     ```

4. **Verify Installation:**
   - After your computer restarts, open **Hyper-V Manager** from the Start menu. If it opens without issues, Hyper-V is installed and ready to use.

### Installation Steps for Windows Server

1. **Install Hyper-V via Server Manager:**
   - Open **Server Manager** and click on **Add roles and features**.
   - In the **Roles** section, select **Hyper-V**.
   - Continue through the wizard and install Hyper-V.
   - Reboot the server when prompted.

2. **Verify Installation:**
   - Once the server restarts, open **Hyper-V Manager** from the Start menu to confirm that Hyper-V has been successfully installed.

---

## 2. Creating a New VM

### Purpose
This section provides step-by-step instructions for creating a new virtual machine in Hyper-V Manager.

### Steps

1. **Open Hyper-V Manager:**
   - Click on the **Start** menu.
   - Search for **Hyper-V Manager** and open the application.

2. **Create a New VM:**
   - In Hyper-V Manager, select the **Hyper-V host** on which you want to create the VM.
   - In the right-hand Actions panel, click **New** and then select **Virtual Machine**.

3. **Configure the VM:**
   - The **New Virtual Machine Wizard** will open. Follow the prompts to configure your VM.
     - **Name the VM**: Enter a meaningful name for the VM.
     - **Location**: Specify where the VM files will be stored, or use the default location.
     - **Generation**: Choose the VM generation (Generation 1 or Generation 2). Generation 2 supports more advanced features, such as secure boot.
     - **Assign Memory**: Set the amount of memory the VM should use.
     - **Configure Network**: Select the virtual network adapter to connect the VM to the network.

4. **Select a Virtual Hard Disk (VHD):**
   - You will be prompted to create a new virtual hard disk (VHD) or use an existing one. Choose **Create a virtual hard disk**.
   - Set the size of the virtual hard disk and specify the location where the VHD should be stored.

5. **Install Operating System:**
   - Choose how you would like to install the operating system:
     - **Install an operating system from a bootable CD/DVD-ROM**: Select an ISO file or physical disc.
     - **Install an operating system later**: If you plan to install later, you can skip this step.

6. **Finish the VM Creation:**
   - Review your settings and click **Finish** to create the VM.

The VM will be listed in Hyper-V Manager, and you can now proceed with further configuration and management.

---

## 3. Configuring VM Resources

### Purpose
This section covers how to configure the CPU, memory, storage, and network resources for your virtual machine in Hyper-V.

### Steps

1. **Configure CPU:**
   - In Hyper-V Manager, right-click on the VM you want to configure and select **Settings**.
   - Under the **Processor** section, you can adjust the number of virtual processors (vCPUs) allocated to the VM.
   - You can also configure **Processor Compatibility Mode** or enable features like **Virtualization Extensions**.

2. **Configure Memory:**
   - In the **Settings** window, under the **Memory** section, adjust the amount of RAM allocated to the VM.
   - You can enable **Dynamic Memory** to allow Hyper-V to adjust the VM’s memory allocation based on demand.

3. **Configure Storage:**
   - Under the **Hard Drive** section in **Settings**, you can add or modify virtual hard disks (VHD or VHDX).
   - To add a new disk, click **Add** and choose **Hard Drive**.
     - Specify the location and size of the new disk, and attach it to the VM.
   - You can also configure **Pass-through disks** if you need direct access to physical disks.

4. **Configure Network Adapter:**
   - Under the **Network Adapter** section in **Settings**, select the virtual switch to connect the VM to the network.
   - If no network adapter is present, click **Add Hardware** and choose **Network Adapter** to add one.
   - Select the appropriate virtual network switch from the drop-down menu.

5. **Additional Resource Configuration:**
   - You can configure other resources like **DVD Drive**, **USB Controller**, and **BIOS/UEFI settings** from the **Settings** window.

Once all resources are configured, click **OK** to save the changes.

---

## 4. Managing VMs

### Purpose
This section covers common management tasks for virtual machines, such as starting, stopping, pausing, snapshotting, cloning, and migrating VMs.

### Steps

1. **Start/Stop a VM:**
   - In Hyper-V Manager, right-click the VM you want to manage.
   - Select **Start** to power on the VM.
   - Select **Stop** to power off the VM.

2. **Pause and Resume a VM:**
   - Right-click the VM and select **Pause** to suspend the VM.
   - To resume, right-click again and select **Resume**.

3. **Take a Snapshot:**
   - Snapshots allow you to capture the state of a VM at a particular moment.
   - Right-click the VM and select **Checkpoint** to create a snapshot.
   - To revert to a snapshot, right-click the VM and select **Apply**.

4. **Clone a VM:**
   - Hyper-V does not have a built-in cloning feature, but you can export and import a VM as a form of cloning.
   - To export, right-click the VM and select **Export**. Choose the destination folder and click **Export**.
   - To import, click **Import Virtual Machine** from the Actions menu, and select the exported VM.

5. **Migrate a VM:**
   - To migrate a VM to another host, right-click the VM and select **Move**.
   - Follow the prompts to select the destination Hyper-V host.
   - Choose whether to move only the VM's data or the entire VM.

6. **VM Integration Services:**
   - Ensure that **Hyper-V Integration Services** are installed on the guest OS to enhance performance and support features like time synchronization and VM shutdown.

---

## Conclusion

By following these steps, helpdesk staff can effectively manage and troubleshoot Hyper-V environments, ensuring that virtual machines are properly created, configured, and maintained. 

For any advanced or troubleshooting tasks, refer to the official Microsoft Hyper-V documentation or contact the system administrator.
