[General IT Documentation](../README.md)
# Active Directory Replication Troubleshooting

Active Directory (AD) replication ensures that changes made to objects on one Domain Controller (DC) are replicated across all other DCs in the domain or forest. Replication issues can lead to inconsistent data, authentication problems, and other disruptions. This guide outlines how to troubleshoot and resolve common Active Directory replication issues.

## Table of Contents

- [Overview of Active Directory Replication](#overview-of-active-directory-replication)
- [Common Replication Issues](#common-replication-issues)
- [Tools for Troubleshooting Replication](#tools-for-troubleshooting-replication)
- [Steps for Troubleshooting Replication Issues](#steps-for-troubleshooting-replication-issues)
    - [Step 1: Check Replication Status](#step-1-check-replication-status)
    - [Step 2: Use Repadmin Tool](#step-2-use-repadmin-tool)
    - [Step 3: Verify Network Connectivity](#step-3-verify-network-connectivity)
    - [Step 4: Check DNS Configuration](#step-4-check-dns-configuration)
    - [Step 5: Examine Event Logs](#step-5-examine-event-logs)
    - [Step 6: Check DHCP Configuration](#step-6-check-dhcp-configuration)
    - [Step 7: Check Site Configuration](#step-7-check-site-configuration)
- [Best Practices for Active Directory Replication](#best-practices-for-active-directory-replication)

## Overview of Active Directory Replication

Replication in Active Directory ensures that changes made on one Domain Controller (DC) are consistently reflected across other DCs in the domain. AD replication is designed to be efficient and reliable, but issues can arise that cause delays or failures in replication.

### Key Replication Components:

- **Domain Controllers**: Servers that hold copies of the AD database and provide authentication services.
- **Sites**: Logical groupings of Domain Controllers that define physical network boundaries for efficient replication.
- **Replication Topology**: The relationship and paths that determine how Domain Controllers replicate with each other.
- **Partitioning**: Different types of AD partitions (e.g., Schema, Configuration, and Domain) determine what data is replicated.

## Common Replication Issues

Here are some common issues that can affect AD replication:

- **Replication Latency**: Delays in replicating changes between DCs.
- **Replication Failure**: Errors in replicating data due to network problems, service failures, or configuration issues.
- **Outdated or Inconsistent Data**: Some DCs may not have the most up-to-date information, causing authentication or authorization issues.
- **DNS Resolution Issues**: Domain Controllers may not be able to locate each other due to DNS misconfiguration.
- **Authentication Errors**: Users may experience login failures if their information is not properly replicated.
- **Event Log Errors**: Error messages in the Directory Service or DNS Server logs may indicate replication issues.

## Tools for Troubleshooting Replication

To troubleshoot replication issues, several tools and utilities can be used:

- **Repadmin**: A command-line tool for managing and troubleshooting replication.  
  **Syntax**: `repadmin /replsummary`  
  This command provides a summary of replication status across Domain Controllers.

- **Dcdiag**: A diagnostic tool to analyze the health of Domain Controllers.  
  **Syntax**: `dcdiag /v`  
  This command runs a detailed diagnostic of the DC’s health, including replication.

- **Event Viewer**: View event logs related to Active Directory, such as replication errors in the Directory Service log.

- **Nltest**: A command-line tool for testing trust relationships and replication status between Domain Controllers.  
  **Syntax**: `nltest /dsgetdc:<domain>`  
  Use this to find the nearest Domain Controller for a given domain.

- **Active Directory Sites and Services**: A Microsoft Management Console (MMC) used for managing replication topology and site configurations.

## Steps for Troubleshooting Replication Issues

### Step 1: Check Replication Status

Use the **Repadmin** tool to check the replication status between Domain Controllers.

```bash
repadmin /replsummary
```
This command will display a summary of replication status, showing if there are any replication failures or delays.

### Step 2: Use Repadmin Tool

For detailed information about replication problems, use the following **Repadmin** commands:

- **Check for replication failures**:
    ```bash
    repadmin /showrepl
    ```

- **Force replication**:
    ```bash
    repadmin /syncall /A /P
    ```

### Step 3: Verify Network Connectivity

Replication between Domain Controllers requires reliable network connectivity. Verify that:

- All Domain Controllers can communicate over the necessary ports (TCP 389, 636, 3268, 3269, and 445).
- There are no firewall or DNS issues blocking communication between DCs.

Run a **ping** or **tracert** command to check network connection:
```bash
ping <domain_controller_name_or_IP>
```

### Step 4: Check DNS Configuration

Since DNS is essential for AD replication, ensure:

- Domain Controllers are using the correct DNS servers.
- DNS Zones (_msdcs, DomainDnsZones) are properly set up and replicating across DCs.
- Dynamic DNS (DDNS) updates are configured for automatic DNS record updates.

To troubleshoot DNS:

- **Verify DNS Resolution**: Run **nslookup** to ensure proper DNS resolution for Domain Controllers:
    ```bash
    nslookup <domain_controller_name>
    ```

- **Test DNS Resolution**: Use PowerShell to confirm that Domain Controllers can resolve each other:
    ```bash
    Resolve-DnsName <domain_controller_name>
    ```

- **Check Event Logs**: Look for DNS-related errors in **Event Viewer > Applications and Services Logs > Microsoft > DNS Server**.

### Step 5: Examine Event Logs

Look for errors that indicate replication issues in the **Directory Service** and **DNS Server** logs.

- **Directory Service Logs**: Check for replication failure events (Event IDs 1311, 1864, 1586, etc.).
- **DNS Server Logs**: Look for DNS resolution errors that could impact replication.

### Step 6: Check DHCP Configuration

If **DHCP** is used for IP address assignment:

- Ensure DHCP and DNS are integrated so that Domain Controllers register their DNS records automatically.

- **Check DHCP Lease Status**: Ensure Domain Controllers have valid leases and proper static IP configurations if using reservations:
    ```bash
    Get-DhcpServerv4Lease -ScopeId <scope_id>
    ```

- **Verify DHCP Configuration**: Confirm that the DHCP server is properly updating DNS records for Domain Controllers.
    - Open **DHCP Management Console** > **Server Options** > **DNS Configuration**.
    - Ensure that **Always update DNS records** is enabled.

- **Ensure Static IPs**: For consistency, use DHCP reservations or static IPs for Domain Controllers.

- **Check DHCP Server Health**: Ensure the DHCP service is running:
    ```bash
    Get-Service -Name dhcpserver
    ```

### Step 7: Check Site Configuration

Incorrect site configuration can affect replication:

- Ensure Domain Controllers are assigned to the correct Active Directory site.
- Verify **Site Links** and **Replication Schedules** in **Active Directory Sites and Services**.

## Best Practices for Active Directory Replication

### 1. Monitor Replication Regularly:
- Set up regular monitoring using tools like **Repadmin**, **Dcdiag**, and **Event Viewer**.
- Consider automating replication health checks and alerts.

### 2. Maintain Correct Time Synchronization:
- Ensure that all Domain Controllers are synchronized to an authoritative time source to avoid replication failures due to time skew.

### 3. Use DNS Best Practices:
- Use **DNS scavenging** to clean up old DNS records.
- Ensure that each Domain Controller has proper DNS entries.

### 4. Minimize Inter-Site Replication Latency:
- Configure replication schedules and site links carefully, especially for remote Domain Controllers with limited bandwidth.

### 5. Backup and Test Recovery Procedures:
- Regularly back up the **Active Directory** database and test disaster recovery procedures to recover from potential replication issues.
