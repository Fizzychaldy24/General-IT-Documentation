[General IT Documentation](../README.md)
# Linux User Management

This document provides a guide on how to add, modify, and manage users in a Linux environment. Understanding user management is essential for administering Linux systems and ensuring proper access control.

## Table of Contents
1. [Introduction to Linux User Management](#introduction-to-linux-user-management)
2. [Adding a User](#adding-a-user)
3. [Modifying User Information](#modifying-user-information)
4. [Deleting a User](#deleting-a-user)
5. [Managing User Groups](#managing-user-groups)
6. [Viewing User Information](#viewing-user-information)

## Introduction to Linux User Management

In Linux, each user has a unique identifier called a **UID** and belongs to one or more **groups**. Proper user management ensures that only authorized users can access certain system resources.

- Users are stored in the `/etc/passwd` file.
- Group memberships are stored in the `/etc/group` file.

## Adding a User

To add a new user to the system, use the `useradd` command. Here's how you can add a user:

### Syntax:
```bash
sudo useradd [options] username
```

### Example:
```bash
sudo useradd -m -s /bin/bash john
```

- `-m` creates the user's home directory.
- `-s` specifies the user's shell (e.g., `/bin/bash`).

### Setting a Password:

After creating the user, set a password using the `passwd` command:

```bash
sudo passwd john
```

You will be prompted to enter and confirm the new password.

## Modifying User Information

You can modify user information such as username, home directory, and shell using the `usermod` command.

### Syntax:
```bash
sudo usermod [options] username
```

### Example: Changing the User's Shell
```bash
sudo usermod -s /bin/zsh john
```
This changes the shell for user `john` to `/bin/zsh`.

### Example: Changing the User's Home Directory
```bash
sudo usermod -d /home/john_new -m john
```
This moves the user's home directory to `/home/john_new`.

## Deleting a User

To remove a user from the system, use the `userdel` command.

### Syntax:
```bash
sudo userdel [options] username
```

### Example: Deleting a User
```bash
sudo userdel john
```

### Removing the User's Home Directory:

To also remove the user's home directory, use the `-r` option:
```bash
sudo userdel -r john
```

## Managing User Groups

Users in Linux can belong to one or more groups. Groups allow for easier management of permissions.

### Adding a User to a Group

To add an existing user to a group, use the `usermod` command with the `-aG` option.

#### Syntax:
```bash
sudo usermod -aG groupname username
```

#### Example: Adding `john` to the `sudo` group
```bash
sudo usermod -aG sudo john
```

### Creating a New Group

To create a new group, use the `groupadd` command:

#### Syntax:
```bash
sudo groupadd groupname
```

#### Example: Creating a new group called `developers`
```bash
sudo groupadd developers
```
## Viewing User Information

You can view user information by inspecting the `/etc/passwd` and `/etc/group` files, or by using the `id` and `getent` commands.

### Viewing a User's Details

To view detailed information about a specific user, use the `id` command:

#### Syntax:
```bash
id username
```

#### Example:
```bash
id john
```

This will show the user's UID, group memberships, and GID.

### Listing All Users

To list all users on the system, you can display the contents of the `/etc/passwd` file:

```bash
cat /etc/passwd
```
