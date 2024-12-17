[General IT Documentation](../README.md)
# PowerShell Scripts Guide

This guide contains several PowerShell scripts for different system tasks including creating user accounts, retrieving system information, and pinging servers. The scripts are organized in the sections below for easy reference.

---

## Table of Contents

1. [Create a New Local User Account](#1-create-a-new-local-user-account)
2. [Get Basic System Information](#2-get-basic-system-information)
3. [Get Network Information (IP, DNS)](#3-get-network-information-ip-dns)
4. [Get System Uptime](#4-get-system-uptime)
5. [Ping Multiple Servers](#5-ping-multiple-servers)

---

## 1. **Create a New Local User Account**

This script creates a new local user account on the machine.

```bash
This script creates a new local user account on the machine.

# Prompt for username and password
$username = Read-Host "Enter the username"
$password = Read-Host "Enter the password" -AsSecureString

# Create the new user
New-LocalUser -Name $username -Password $password -FullName "$username User" -Description "New User Account" -AccountNeverExpires

# Add the new user to the 'Users' group
Add-LocalGroupMember -Group "Users" -Member $username

Write-Host "User $username created and added to the Users group."
```

---

## 2. **Get Basic System Information**

This script retrieves basic system information such as the OS version, CPU, memory, and disk space.

```bash
Get Basic System Information
This script retrieves basic system information like the OS version, CPU, memory, and disk space.

Script:
# Get OS Information
$os = Get-CimInstance -ClassName Win32_OperatingSystem
Write-Host "OS: $($os.Caption)"
Write-Host "Version: $($os.Version)"
Write-Host "Architecture: $($os.OSArchitecture)"

# Get CPU Information
$cpu = Get-CimInstance -ClassName Win32_Processor
Write-Host "CPU: $($cpu.Name)"

# Get Total Physical Memory
$memory = Get-CimInstance -ClassName Win32_ComputerSystem
Write-Host "Total Physical Memory: $([math]::round($memory.TotalPhysicalMemory / 1GB, 2)) GB"

# Get Disk Space Information
$disks = Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3"
$disks | ForEach-Object {
    Write-Host "$($_.DeviceID): $([math]::round($_.Size / 1GB, 2)) GB Total, $([math]::round($_.FreeSpace / 1GB, 2)) GB Free"
}
```

---

## 3. **Get Network Information (IP, DNS)**

This script retrieves the computer's IP address and DNS information.

```bash
Get Network Information (IP, DNS)
This script retrieves the computer's IP address and DNS information.

# Get IP Address
$ipConfig = Get-NetIPAddress -AddressFamily IPv4 | Where-Object {$_.InterfaceAlias -ne "Loopback" }
Write-Host "IP Address: $($ipConfig.IPAddress)"

# Get DNS Servers
$dnsServers = Get-DnsClientServerAddress | Where-Object {$_.InterfaceAlias -ne "Loopback"}
Write-Host "DNS Servers: $($dnsServers.ServerAddresses -join ', ')"
```

---

## 4. **Get System Uptime**

This script shows how long the system has been running.
```bash
Get System Uptime
This script shows how long the system has been running.

# Get system uptime
$uptime = (Get-CimInstance -ClassName Win32_OperatingSystem).LastBootUpTime
$uptimeFormatted = (Get-Date) - $uptime
Write-Host "System Uptime: $($uptimeFormatted.Days) days, $($uptimeFormatted.Hours) hours, $($uptimeFormatted.Minutes) minutes"
```

---

## 5. **Ping Multiple Servers**

This script pings multiple servers and checks if they are reachable.

Ping Multiple Servers
This script pings multiple servers and checks if they are reachable.

# List of servers to ping
```bash
$servers = @("192.168.1.1", "google.com", "8.8.8.8")

foreach ($server in $servers) {
    Write-Host "Pinging $server..."
    $pingResult = Test-Connection -ComputerName $server -Count 1 -Quiet
    if ($pingResult) {
        Write-Host "$server is reachable."
    } else {
        Write-Host "$server is unreachable."
    }
}
````

---

### Conclusion

These scripts allow you to automate various tasks in PowerShell, including creating user accounts, retrieving system information, and network diagnostics. You can modify or expand upon these scripts as needed for your system management tasks.
