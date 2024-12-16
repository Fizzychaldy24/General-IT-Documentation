# General IT Documentation

This repository contains a variety of resources, guides, and troubleshooting documentation on common IT-related tasks, such as setting up and managing **hypervisors**, configuring **ticketing systems**, hosting websites, and other IT infrastructure topics.

Whether you are a helpdesk technician, system administrator, or IT specialist, you will find helpful guides and configuration examples here for a wide range of IT operations.

## Table of Contents

- [Troubleshooting Guides](#troubleshooting-guides)
- [System Administration](#system-administration)
- [Hypervisors](#hypervisors)
- [Ticketing Systems](#ticketing-systems)
- [Web Hosting](#web-hosting)
- [Scripts](#scripts)
- [How to Use](#how-to-use)
- [Contributing](#contributing)
- [Contact](#contact)

## Introduction

This repository provides various documentation and configuration guides that cover the essential aspects of managing IT infrastructure, including virtualization, web hosting, helpdesk systems, and more. The content is organized by topic to help guide IT professionals in resolving common issues and deploying best practices.

## Troubleshooting Guides

This repository also contains troubleshooting documentation for common IT problems, including hardware, software, and network issues.

### Examples:
- **Internet Connectivity Issues**: Step-by-step guide for troubleshooting network problems.
- **Disk Space Problems**: How to identify and resolve low disk space issues.
- **Slow Computer Performance**: Tips and tools for diagnosing performance issues.

#### Documentation:
- [Troubleshooting Guides](Troubleshooting%20Guides/IT%20Troubleshooting%20Documentation.md) - A comprehensive collection of guides designed to help you solve common IT problems related to networking, hardware, and system performance.

## System Administration

This section contains useful guides on managing and configuring systems, including **Linux**, **Windows**, **macOS** environments, network configuration, and system security.

### Topics Include:
- **Linux Administration**: Service management, scripting, and user management in Linux environments.
- **macOS Administration**: Managing system settings, file, and folder permissions on user accounts in macOS.
- **Windows Active Directory**: Active Directory setup, user/group management, and troubleshooting.
- **Networking Basics**: IP addressing, firewall rules, and VPN configuration.

#### Resources:
- [Linux Administration](System%20Administration/Linux%20Administration/Linux-README.md) - Service management, scripting, adding/removing users in Linux environments.
- [macOS Administrations](System%20Administration/Mac%20OS%20Administration/README.md) - Instructions on managing system settings and user account file/folder permissions in macOS.
- [Windows AD](System%20Administration/Windows%20Administration/README.md) - Active Directory Setup, user/group management, Group Policies, and replication troubleshooting.
- [Network Configuration Basics](Network%20Administration/Network%20Configuration%20Basics.md) - Best practices for setting up network services and securing your network.

## Hypervisors

### Virtualization Platforms Supported:
- **VMware vSphere/ESXi**: Documentation on installation, setup, and management.
- **Microsoft Hyper-V**: Guides for installation, configuration, and troubleshooting virtual machines.

**Key Tasks for Helpdesk:**

    VMware vSphere/ESXi:
        How to create and manage virtual machines (VMs).
        Monitoring VM health and performance.
        Managing storage and networking for VMs.
        
    Microsoft Hyper-V:
        How to configure and manage Hyper-V environments.
        Creating, starting, and stopping VMs.
        Troubleshooting VM connectivity and performance issues.
  
#### Resources:
- [Hyper-V Setup Guide](hypervisors/hyperv-setup.md) - Setup, installation, and management.
- [VMware vSphere Best Practices](hypervisors/vmware-best-practices.md) - Setup, installation, and management.

## Ticketing Systems

This section provides guides and best practices for setting up and configuring ticketing systems for IT helpdesk support.

### Supported Ticketing Systems:
- **Jira Service Management**: Setup and configuration, integrations, and workflows.
- **Zendesk**: Installation and configuration, ticket management, and automation.
- **Freshservice**: How to configure and manage incidents, changes, and assets.

**Common Tasks for Helpdesk:**

    Jira Service Management:
        Creating and managing tickets: How to create, update, and resolve support tickets.
        Ticket workflows: Setting up workflows for ticket routing, escalation, and closure.
        Integrations: Connecting Jira with other systems like email, Slack, or asset management tools.

    Zendesk:
        Creating tickets: How to create and manage tickets using Zendesk.
        Ticket routing: Using triggers, automations, and views to manage ticket flow.
        Customer communication: How to respond to tickets effectively and track interactions.

    Freshservice:
        Incident management: Creating, updating, and closing incidents.
        Asset management: How to manage assets and link them to tickets.
        Change management: Setting up and managing change requests in Freshservice.

#### Resources:
- [Jira Service Management Setup](ticketing-systems/jira-setup.md) - A step-by-step guide on setting up Jira for IT support.
- [Zendesk Ticket Workflow](ticketing-systems/zendesk-workflow.md) - How to streamline your ticket management process with workflows in Zendesk.
- [Freshservice Configuration](ticketing-systems/freshservice-config.md) - Guide to configuring Freshservice for efficient incident and change management.

## Scripts

This section provides a collection of useful scripts for automating IT tasks, system administration, troubleshooting, and more. These scripts are designed to simplify and speed up common IT operations across different platforms and environments.

#### Examples:
- **Linux User Management Script**: A Bash script for adding, modifying, and deleting user accounts.
- **Windows Service Status Checker**: PowerShell script to check the status of critical services on Windows servers.
- **Network Troubleshooting Script**: A Python script that automates the process of diagnosing network connectivity issues.

#### Resources:
- [Linux User Management Script](scripts/linux-user-management.sh) - A script to manage user accounts in Linux.
- [Windows Service Status Checker](scripts/windows-service-check.ps1) - PowerShell script to check the status of services on Windows machines.
- [Network Troubleshooting Script](scripts/network-troubleshooting.py) - A Python script that checks network connectivity and generates a report.

## How to Use

1. **Clone the Repository**:
   To get started, clone the repository to your local machine:
   ```bash
   git clone https://github.com/Fizzychaldy24/General-IT-Documentation.git

## Contributing

We welcome contributions to improve this documentation. If you’d like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your changes.
3. Make your changes and write clear commit messages.
4. Submit a pull request with a description of the changes you’ve made.

### Guidelines:

- Ensure that any new documentation is clear, concise, and accurate.
- Follow the same formatting as existing documentation for consistency.
- If adding new topics, ensure they are categorized appropriately in the Table of Contents.

## Contact

For any inquiries, please reach out to ernestoangel202@gmail.com.
