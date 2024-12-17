[General IT Documentation](/README.md)
# Hyper-V Network Configuration and Troubleshooting Guide

## Overview
This document provides helpdesk staff with a step-by-step guide to configuring and troubleshooting networking in a Hyper-V environment. It covers how to create virtual switches, configure network adapters for VMs, and diagnose common network-related issues, such as connectivity problems, VLAN configurations, and network isolation.

---

## Table of Contents
1. [Setting Up Virtual Switches](#1-setting-up-virtual-switches)
2. [Configuring Network Adapters](#2-configuring-network-adapters)
3. [Troubleshooting Network Issues](#3-troubleshooting-network-issues)

---

## 1. Setting Up Virtual Switches

### Purpose
Virtual switches in Hyper-V enable VMs to connect to the physical network and communicate with other VMs. This section covers the creation and configuration of different types of virtual switches: **External**, **Internal**, and **Private**.

### Steps

1. **Creating a Virtual Switch**:
   - Open **Hyper-V Manager**.
   - In the **Actions** pane, click **Virtual Switch Manager**.
   - Choose the appropriate type of virtual switch based on your needs:
     - **External Virtual Switch**: Connects the VM to the physical network (e.g., internet access).
     - **Internal Virtual Switch**: Allows communication between the VM and the host but not the external network.
     - **Private Virtual Switch**: Limits communication to the VM only; no access to the host or external network.

2. **Configuring an External Virtual Switch**:
   - Select **External** and click **Create Virtual Switch**.
   - Name the switch (e.g., "External Network").
   - Under **Connection Type**, select the physical network adapter to bind the virtual switch to. This is the physical NIC that will provide internet or network access to VMs.
   - Optionally, check **Allow management operating system to share this network adapter** if you want the host OS to share the same network connection as the VMs.
   - Click **OK** to create the switch.

3. **Configuring an Internal or Private Virtual Switch**:
   - For **Internal**, select **Internal** and click **Create Virtual Switch**.
     - This type allows communication between the host and VMs but blocks external access.
   - For **Private**, select **Private** and click **Create Virtual Switch**.
     - This type only allows communication between VMs and does not permit any traffic to or from the host or external network.
   - Click **OK** to finish the configuration.

---

## 2. Configuring Network Adapters

### Purpose
Network adapters in Hyper-V connect virtual machines to virtual switches. This section covers how to add and configure network adapters for VMs in Hyper-V.

### Steps

1. **Adding a Network Adapter to a Virtual Machine**:
   - Open **Hyper-V Manager** and select the VM you want to configure.
   - Right-click the VM and choose **Settings**.
   - In the **Settings** window, click **Add Hardware**.
   - Select **Network Adapter** and click **Add**.
   - Under **Network Adapter**, select the virtual switch to which you want to connect the VM. For example, if you're connecting the VM to the external network, select the **External Virtual Switch** created in the previous section.
   - Click **OK** to save the configuration.

2. **Configuring Advanced Network Adapter Settings**:
   - In the **VM Settings** window, under **Network Adapter**, you can configure additional settings:
     - **MAC Address**: Assign a static or dynamic MAC address to the adapter.
     - **Virtual Switch**: Select or change the connected virtual switch.
     - **Bandwidth Management**: Set limits on bandwidth usage for the adapter (optional).
     - **VLAN ID**: If the network uses VLAN tagging, enter the appropriate VLAN ID to assign the VM to a specific VLAN.
   - Click **OK** to save changes.

3. **Configuring Multiple Network Adapters**:
   - You can configure more than one network adapter for a VM if needed.
     - In **VM Settings**, click **Add Hardware**, select **Network Adapter**, and click **Add** again to configure additional adapters.
   - Each network adapter can be connected to a different virtual switch depending on your network setup.

---

## 3. Troubleshooting Network Issues

### Purpose
This section provides guidance on diagnosing and fixing common network-related issues that can arise in a Hyper-V environment, including connectivity issues, VLAN misconfigurations, and network isolation.

### Steps

1. **Diagnosing VM Connectivity Issues**:
   - **Verify the Network Adapter Configuration**: Ensure that the VM has a network adapter attached to the correct virtual switch and that it is configured properly.
   - **Check VM Network Settings**: Inside the VM, verify the network settings (e.g., IP address, DNS servers). Ensure that the VM is configured for the correct network (e.g., DHCP or static IP).
   - **Ping Test**: From within the VM, run a `ping` test to both local and external addresses:
     - `ping 127.0.0.1` (to check if the network stack is functioning).
     - `ping <VM's gateway>` (to check if the VM can reach its gateway).
     - `ping <external address>` (to check if the VM can reach the external network).
   - **Check Virtual Switch Connection**: Ensure that the virtual switch is correctly linked to a physical network adapter if using an **External Virtual Switch**.

2. **VLAN Misconfiguration Issues**:
   - **Verify VLAN ID**: If the VM is configured for a specific VLAN, verify that the correct VLAN ID is assigned to the VM’s network adapter.
     - In **Hyper-V Manager**, under **Settings** → **Network Adapter**, ensure that the **VLAN ID** is correctly set if the network is VLAN-tagged.
   - **Check Physical Network Switch**: Ensure that the physical switch that connects the Hyper-V host is correctly configured to support the VLAN being used by the VM.

3. **Network Isolation Issues (Private/Internal Switches)**:
   - **Private Virtual Switch**: If the VM is connected to a **Private Virtual Switch**, ensure that you understand it will only communicate with other VMs connected to the same switch. It will not have access to the host or the external network.
   - **Internal Virtual Switch**: If the VM is connected to an **Internal Virtual Switch**, it should be able to communicate with the host. Check that the host's network adapter is properly configured and not blocking internal communications.
   - **Test with Different Switch Type**: If network isolation is suspected, try switching to an **External Virtual Switch** to confirm whether the issue lies with network isolation.

4. **Hyper-V Virtual Switch Misconfigurations**:
   - **Virtual Switch Manager**: Open the **Virtual Switch Manager** in **Hyper-V Manager** and ensure the virtual switch is correctly configured and connected to the appropriate physical network adapter for external access.
   - **Network Adapter Drivers**: Ensure that the virtual network adapters on the Hyper-V host are correctly configured, and check for driver updates for the physical NIC.
   - **Restart Network Services**: Sometimes network issues can be resolved by restarting network services on both the Hyper-V host and the guest VM.

5. **Network Performance Issues**:
   - **Check for Network Saturation**: Use **Performance Monitor** on both the host and the VM to monitor network utilization (bytes received/sent per second).
   - **Adjust Bandwidth Settings**: In **VM Settings**, ensure that bandwidth management settings are not limiting network throughput.
   - **VM Integration Services**: Make sure that **Hyper-V Integration Services** are installed and up-to-date on the guest VMs, as outdated integration tools can affect network performance.

---

## Conclusion

This guide provides helpdesk staff with the knowledge to configure, manage, and troubleshoot networking in Hyper-V environments. By following the steps for creating virtual switches, configuring network adapters, and troubleshooting network issues, your team can ensure that VMs have reliable and efficient network connectivity.

For complex network-related issues or persistent problems, consult Hyper-V documentation or escalate the issue to your network administrator.
