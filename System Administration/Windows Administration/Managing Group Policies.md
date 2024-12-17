[General IT Documentation](../README.md)
# Managing Group Policies

Group Policy is a powerful tool for administrators to configure and manage the settings and permissions across users and computers in an Active Directory (AD) environment. It allows centralized management and configuration of operating systems, applications, and user settings. This guide will walk you through how to configure and manage **Group Policy Objects (GPOs)** in Active Directory.

## Table of Contents
1. [Understanding Group Policy](#understanding-group-policy)
2. [Creating a Group Policy Object (GPO)](#creating-a-group-policy-object-gpo)
3. [Linking GPOs to Active Directory Containers](#linking-gpos-to-active-directory-containers)
4. [Configuring Group Policy Settings](#configuring-group-policy-settings)
5. [Testing and Enforcing GPOs](#testing-and-enforcing-gpos)
6. [Troubleshooting Group Policies](#troubleshooting-group-policies)
7. [Best Practices for Group Policy Management](#best-practices-for-group-policy-management)

## Understanding Group Policy

Group Policy allows administrators to define user and computer configurations within an Active Directory domain. A **Group Policy Object (GPO)** is a container for settings that dictate how systems behave, such as:

- **Security settings** (password policies, lockout policies)
- **User settings** (desktop backgrounds, Start menu configurations)
- **Computer settings** (software installation, Windows Update settings)

These policies can be applied to **organizational units (OUs)**, **sites**, or the **domain** itself.

### Group Policy Components:
- **Group Policy Object (GPO)**: The container for the actual policy settings.
- **Group Policy Management Console (GPMC)**: A tool used to manage GPOs.
- **Group Policy Client**: The service on client machines that applies the policies.

## Creating a Group Policy Object (GPO)

To create a new GPO:

1. **Open Group Policy Management Console (GPMC)**:
   - Click on **Start**, then search for **Group Policy Management**.
   - Alternatively, go to **Server Manager** > **Tools** > **Group Policy Management**.

2. **Navigate to the Domain or OU**:
   - In the **GPMC**, expand your **forest** > **Domains**, then right-click the domain or Organizational Unit (OU) where you want to create the GPO.

3. **Create a New GPO**:
   - Right-click on the **Group Policy Objects** folder and select **New**.
   - Enter a descriptive name for the GPO (e.g., **Password Policy Settings**), and click **OK**.

4. **Edit the GPO**:
   - Right-click the new GPO and select **Edit**. This opens the **Group Policy Management Editor**, where you can configure settings.

## Linking GPOs to Active Directory Containers

Once a GPO is created, you need to link it to a specific **site**, **domain**, or **organizational unit (OU)**.

1. **Link a GPO to the Domain or OU**:
   - In **Group Policy Management Console (GPMC)**, right-click the **domain** or **OU** you want to link the GPO to.
   - Select **Link an Existing GPO**.
   - Select the GPO you created earlier from the list and click **OK**.

2. **Group Policy Inheritance**:
   - If there are multiple GPOs linked to a site, domain, or OU, the settings from those GPOs are combined.
   - GPOs linked at a higher level (e.g., domain) will apply to lower levels (e.g., OU) unless blocked or overridden.

## Configuring Group Policy Settings

Group Policy settings are divided into **Computer Configuration** and **User Configuration** sections.

### Computer Configuration
These settings apply to computer accounts and are processed when the computer starts or logs on.

- **Path**: `Computer Configuration` > `Policies` > `Administrative Templates`
- Example settings:
  - Software installation
  - Windows Update settings
  - Security options (password policies, lockout policies)
  - Network settings

### User Configuration
These settings apply to user accounts and are processed when the user logs on.

- **Path**: `User Configuration` > `Policies` > `Administrative Templates`
- Example settings:
  - Desktop wallpaper
  - Start menu and taskbar configurations
  - Folder redirection
  - Software restrictions

### Steps to Configure Settings:
1. In the **Group Policy Management Editor**, navigate to the desired setting (either under **Computer Configuration** or **User Configuration**).
2. Double-click the setting you want to configure.
3. Choose one of the following:
   - **Enabled**: Activates the policy.
   - **Disabled**: Deactivates the policy.
   - **Not Configured**: Leaves the policy unset (default behavior).
4. Click **OK** to save your changes.

### Example: Enforcing a Password Policy
1. In the **GPMC**, right-click the GPO you want to edit and select **Edit**.
2. Navigate to `Computer Configuration` > `Policies` > `Windows Settings` > `Security Settings` > `Account Policies` > `Password Policy`.
3. Double-click **Minimum Password Length** and set the desired length (e.g., 8 characters).
4. Click **OK** to save the setting.

## Testing and Enforcing GPOs

### Force a GPO Update:
To force a GPO update on a client machine, run the following command in **Command Prompt** (as Administrator):

```bash
gpupdate /force
```

### Check GPO Application:

You can check which GPOs are applied on a specific machine or user by using the following command:

```bash
gpresult /R
```

This will show a summary of the GPOs applied to the computer and user.

### GPO Modeling and Resultant Set of Policy (RSoP):

- **Group Policy Modeling**: Simulate GPO application to see how policies will affect users or computers before applying them.
    - In the GPMC, right-click **Group Policy Modeling**, then select **Group Policy Modeling Wizard**.
- **Resultant Set of Policy (RSoP)**: Shows the final set of policies applied to a machine or user.
    - In GPMC, right-click **Resultant Set of Policy** and select **RSoP Wizard** to generate a report.

## Troubleshooting Group Policies

### Check GPO Application:
- Ensure the GPO is properly linked to the correct domain, OU, or site.
- Use `gpresult` to check the GPOs applied to the client.

### Ensure GPO Permissions:
- Verify that the correct users or computers have permission to apply the GPO. Right-click the GPO in GPMC and select **Edit**, then go to the **Delegation** tab.

### Use the Group Policy Results Tool:
- This tool helps you understand which GPOs were applied and why. You can run it from GPMC to analyze the GPO results on a specific computer or user.

### Check Event Logs:
- If GPOs are not applying as expected, check the Event Viewer for related errors under **Applications and Services Logs > Microsoft > Windows > GroupPolicy**.

## Best Practices for Group Policy Management

### Use Descriptive Naming Conventions:
- Name your GPOs based on their purpose, such as **Password Policy GPO**, **Software Deployment GPO**, etc.

### Avoid Using Too Many GPOs:
- Keep the number of GPOs manageable to prevent complexity and performance issues.

### Test GPOs Before Deployment:
- Always test new GPOs on a limited set of users or computers to avoid unwanted changes across the entire domain.

### Use GPO Inheritance Wisely:
- Be mindful of inheritance when linking GPOs to domains, OUs, or sites. Block inheritance only when absolutely necessary.

### Regularly Review GPOs:
- Periodically review your GPOs to ensure they still align with the organization's policies and security requirements.

### Backup GPOs:
- Regularly back up GPOs using the **Group Policy Management Console** to ensure you can restore them in case of accidental deletion or misconfiguration.

### Use Group Policy Preferences:
- For advanced configuration, use **Group Policy Preferences** to set more granular settings, such as mapped drives or scheduled tasks.
