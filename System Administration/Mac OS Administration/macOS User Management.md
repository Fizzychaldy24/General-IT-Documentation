[System Administration](../README.md)
# macOS User Management

This guide covers how to add, modify, and manage users on a **macOS** system. You will learn how to create new users, modify user details, and manage existing user accounts using both the **System Preferences** interface and **Terminal** commands.

## Table of Contents

1. [Adding a New User](#adding-a-new-user)
2. [Modifying an Existing User](#modifying-an-existing-user)
3. [Managing User Groups](#managing-user-groups)
4. [Deleting a User](#deleting-a-user)
5. [Using Terminal for User Management](#using-terminal-for-user-management)

## Adding a New User

To add a new user in macOS:

### Method 1: Using System Preferences

1. Open **System Preferences** from the Apple menu.
2. Go to **Users & Groups**.
3. Click the **lock** icon in the bottom-left corner to unlock the settings (you may need to enter your administrator password).
4. Click the **+** button below the user list.
5. Choose the account type (Administrator, Standard, Managed with Parental Controls, or Sharing Only).
6. Fill in the required fields:
   - **Full Name**
   - **Account Name** (this will be used for the user folder and username)
   - **Password** and **Verify** (set a secure password)
7. Click **Create User**.

### Method 2: Using Terminal

To add a new user via the Terminal, follow these steps:

1. Open **Terminal** (Applications > Utilities > Terminal).
2. Run the following command to create a new user:

    ```bash
    sudo sysadminctl -addUser <username> -fullName "<full name>" -password "<password>"
    ```

   Replace `<username>`, `<full name>`, and `<password>` with the desired values.

3. Press Enter and provide your administrator password when prompted.

## Modifying an Existing User

To modify an existing user:

### Method 1: Using System Preferences

1. Open **System Preferences** and go to **Users & Groups**.
2. Click the **lock** icon to unlock the settings.
3. Select the user you want to modify from the list.
4. You can change:
   - **Account Name** (requires the user to be logged out)
   - **Password** (click the **Reset Password** button)
   - **Full Name**
5. Make the necessary changes and close the window when done.

### Method 2: Using Terminal

To change a user's full name or password, use the following commands:

1. **Change Full Name:**

    ```bash
    sudo usermod -c "New Full Name" <username>
    ```

2. **Change Password:**

    ```bash
    sudo passwd <username>
    ```

   You will be prompted to enter the new password for the user.

## Managing User Groups

To manage user groups:

1. **List User Groups:**

    To list the groups a user belongs to:

    ```bash
    groups <username>
    ```

2. **Add User to Group:**

    To add a user to a group, use the following command:

    ```bash
    sudo dscl . -append /Groups/<groupname> GroupMembership <username>
    ```

3. **Remove User from Group:**

    To remove a user from a group:

    ```bash
    sudo dscl . -delete /Groups/<groupname> GroupMembership <username>
    ```

## Deleting a User

To delete a user:

### Method 1: Using System Preferences

1. Open **System Preferences** and go to **Users & Groups**.
2. Click the **lock** icon to unlock the settings.
3. Select the user you want to delete.
4. Click the **-** button below the user list.
5. Choose whether to **Save the home folder in a disk image**, **Don't change the home folder**, or **Delete the home folder**.
6. Click **Delete User**.

### Method 2: Using Terminal

To delete a user using the Terminal:

1. Open **Terminal**.
2. Run the following command:

    ```bash
    sudo sysadminctl -deleteUser <username>
    ```

   This will delete the user account and optionally remove the user's home directory.

## Using Terminal for User Management

macOS offers various command-line tools for managing users:

1. **List all users:**

    ```bash
    dscl . list /Users
    ```

2. **Show user details:**

    To view user details (e.g., groups and attributes):

    ```bash
    dscl . read /Users/<username>
    ```

3. **Disable a user account:**

    To disable a user account without deleting it:

    ```bash
    sudo dscl . -create /Users/<username> UserShell /usr/bin/false
    ```

4. **Enable a user account:**

    To re-enable a disabled user account:

    ```bash
    sudo dscl . -create /Users/<username> UserShell /bin/bash
    ```

---

## Conclusion

This guide provided you with instructions on how to add, modify, manage, and delete users in macOS, both using the graphical **System Preferences** interface and through **Terminal** commands. Understanding these commands and tools will help you effectively manage user accounts and permissions in macOS.

For more advanced user management, you can explore additional tools such as **dscl** (Directory Service command line utility) and **sysadminctl** for further administrative control.
