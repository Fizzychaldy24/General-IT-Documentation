[System Administration](../README.md)
# Bash Scripts Collection

## Table of Contents
1. [System Information Script](#system-information-script)
2. [Create a New User Script](#create-a-new-user-script)
3. [Delete Old Files Script](#delete-old-files-script)
4. [Top 10 Processes by Memory Usage](#top-10-processes-by-memory-usage)
5. [Update and Upgrade System](#update-and-upgrade-system)

---

## System Information Script

This script gives you basic system information such as uptime, disk usage, memory usage, and CPU info.
```bash
#!/bin/bash

echo "System Information"
echo "-------------------"
echo "Uptime: $(uptime -p)"
echo "Disk Usage: $(df -h /)"
echo "Memory Usage: $(free -h)"
echo "CPU Info: $(lscpu | grep 'Model name')"
echo "Hostname: $(hostname)"
```

---

## Create a New User Script

This script automates the process of creating a new user on the system.

```bash
#!/bin/bash

# Prompt for username and password
read -p "Enter the username: " USERNAME
read -sp "Enter the password: " PASSWORD

# Create user and set password
sudo useradd -m -s /bin/bash $USERNAME
echo "$USERNAME:$PASSWORD" | sudo chpasswd

echo "User $USERNAME created successfully."
```

---

## Delete Old Files Script

This script deletes files in a directory that are older than a certain number of days.

```bash
#!/bin/bash

TARGET_DIR="/home/user/Downloads"
DAYS=30

echo "Deleting files older than $DAYS days in $TARGET_DIR..."
find $TARGET_DIR -type f -mtime +$DAYS -exec rm -f {} \;
echo "Deletion complete."
```

---

## Top 10 Processes by Memory Usage

This script lists the top 10 processes consuming the most memory.

```bash
#!/bin/bash

echo "Top 10 processes by memory usage:"
ps aux --sort=-%mem | head -n 11
```

---

## Update and Upgrade System

This script updates and upgrades your Ubuntu system, keeping everything up to date.

```bash
#!/bin/bash

echo "Updating package list..."
sudo apt update

echo "Upgrading packages..."
sudo apt upgrade -y

echo "Cleaning up unnecessary packages..."
sudo apt autoremove -y
```

---

This markdown document includes the table of contents and placeholders for each script. You can copy this content into a `.md` file and add the corresponding scripts where indicated.
