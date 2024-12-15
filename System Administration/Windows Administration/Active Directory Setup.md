# Active Directory Setup

This guide provides a step-by-step process for installing and configuring **Active Directory Domain Services (AD DS)** on **Windows Server**. By the end of this guide, you'll have a functional Active Directory Domain Controller to manage user accounts, computers, and other network resources.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Installing the Active Directory Domain Services Role](#installing-the-active-directory-domain-services-role)
3. [Promoting the Server to a Domain Controller](#promoting-the-server-to-a-domain-controller)
4. [Configuring Active Directory](#configuring-active-directory)
5. [Verifying Active Directory Installation](#verifying-active-directory-installation)

## Prerequisites

Before you begin, ensure the following:

- You are using **Windows Server 2012** or later.
- The server should have a static IP address.
- You have administrative privileges on the server.

### System Requirements:
- **CPU**: 1.4 GHz 64-bit processor or higher.
- **RAM**: Minimum of 2 GB of RAM.
- **Disk Space**: At least 40 GB of free space.

## Installing the Active Directory Domain Services Role

1. **Open Server Manager**:
   - Click on the **Start** button, then select **Server Manager** from the list.

2. **Add Roles and Features**:
   - In **Server Manager**, click **Manage** at the top right and select **Add Roles and Features**.

3. **Role-Based or Feature-Based Installation**:
   - Select **Role-based or feature-based installation** and click **Next**.

4. **Select Server**:
   - Choose the server where you want to install Active Directory and click **Next**.

5. **Select Active Directory Domain Services**:
   - On the **Select features** screen, ensure that **Active Directory Domain Services** is selected, and click **Next**.

6. **Install AD DS**:
   - On the **Confirmation** screen, review your selections and click **Install**. The installation process will begin. Wait for it to complete.

7. **Restart Server**:
   - After installation, you might need to restart the server for the changes to take effect.

## Promoting the Server to a Domain Controller

1. **Open Server Manager**:
   - After the installation is complete, click the **Notifications** flag in **Server Manager** and select **Promote this server to a domain controller**.

2. **Deployment Configuration**:
   - On the **Deployment Configuration** screen, select **Add a new forest** if this is the first domain controller in the network.
   - Enter a **Root domain name** (e.g., `example.com`).
   - Click **Next**.

3. **Domain Controller Options**:
   - Choose the **Domain Functional Level** and **Forest Functional Level** (for most setups, you can leave it as default, usually Windows Server 2016).
   - Set the **Directory Services Restore Mode (DSRM) password**. This password is required for restoring Active Directory in case of system failure.
   - Click **Next**.

4. **DNS Options**:
   - If prompted, click **Next** to confirm the DNS delegation, as this server will also function as a DNS server for the domain.

5. **Additional Options**:
   - Review the options and click **Next**.

6. **Paths**:
   - You can leave the default paths for the AD database, log files, and SYSVOL, or change them as needed. Click **Next**.

7. **Review Options**:
   - Review all the selections and click **Next**.

8. **Install and Reboot**:
   - Click **Install**. The system will promote the server to a domain controller and automatically restart.

## Configuring Active Directory

1. **Log into the Domain**:
   - After the server restarts, log in using the **Domain Administrator** account (e.g., `Administrator@example.com`).

2. **Access Active Directory Users and Computers**:
   - Open **Server Manager** and select **Tools**, then click on **Active Directory Users and Computers**.

3. **Create Organizational Units (OUs)**:
   - In the **Active Directory Users and Computers** window, right-click on the domain name and select **New** > **Organizational Unit** to create OUs for organizing users, computers, and other resources.

4. **Create User Accounts**:
   - Right-click on the desired **Organizational Unit (OU)**, and select **New** > **User**.
   - Fill in the required fields (e.g., First Name, Last Name, User Logon Name) and set the password.

5. **Create Groups**:
   - Right-click on the domain or an Organizational Unit (OU), select **New** > **Group** to create groups for organizing users based on their roles.

## Verifying Active Directory Installation

1. **Check Domain Controller Functionality**:
   - Open a **Command Prompt** and run the following command to ensure the domain controller is functioning properly:
     ```bash
     dcdiag
     ```
   - The `dcdiag` tool will run a series of tests to verify the health of the domain controller.

2. **Verify DNS Resolution**:
   - Check that the DNS server is functioning correctly by using the `nslookup` command:
     ```bash
     nslookup example.com
     ```

3. **Check Replication Status**:
   - If you have multiple domain controllers, ensure that replication is working properly by using:
     ```bash
     repadmin /replsummary
     ```

4. **Log into the Domain**:
   - Try logging into a client machine using the domain account to verify that the server is correctly configured.

## Conclusion

You've successfully installed and configured **Active Directory Domain Services (AD DS)** on a Windows Server. Now you can manage users, groups, and other resources in your domain. To expand your AD infrastructure, consider configuring Group Policy, setting up additional domain controllers, or integrating with other services like DNS and DHCP.

For more advanced configurations, explore **Group Policy** management, **Active Directory Federation Services (ADFS)**, or **Active Directory Certificate Services (ADCS)** for a complete enterprise solution.
