[General IT Documentation](../README.md) | [Ticketing Systems](../README.md) | [System Administrasion](../README.md)
# IT Troubleshooting Documentation

## Table of Contents
1. [Internet Connection Issues](#1-internet-connection-issues)
2. [Printer Not Responding](#2-printer-not-responding)
3. [Slow Computer Performance](#3-slow-computer-performance)
4. [Forgotten Password](#4-forgotten-password)
5. [System Crashing or Freezing](#5-system-crashing-or-freezing)
6. [Software Not Opening or Crashing](#6-software-not-opening-or-crashing)
7. [Account Access Issues](#7-account-access-issues)
8. [Hardware & Peripheral Troubleshooting](#8-hardware--peripheral-troubleshooting)

---

## 1. Internet Connection Issues

**Symptoms:** User cannot connect to the internet or is experiencing slow speeds.

**Troubleshooting Guide:**

1. **Check Physical Connections:**
   - Ensure the Ethernet cable is properly connected or that the Wi-Fi is enabled on the device.
   - Check the modem/router lights. Typically, a "green" or stable light indicates proper function.

2. **Verify Network Status:**
   - Check if the issue is isolated to one device or if others are also affected. If others are also having issues, it could be a router or ISP problem.

3. **Restart Router and Computer:**
   - Power cycle the router and restart the computer. This often resolves temporary connectivity issues by resetting network settings.

4. **Check IP Configuration:**
   - Ensure the computer is set to receive an IP address automatically from the router (DHCP).
   - On **Windows**: Open Command Prompt and type `ipconfig` to verify IP address configuration.
   - On **Mac**: Go to **System Preferences** > **Network** and ensure it's set to "Using DHCP."

5. **Run Network Diagnostics:**
   - Use the built-in network diagnostics tool.
     - **Windows**: Right-click on the network icon > **Troubleshoot problems**.
     - **Mac**: Go to **System Preferences** > **Network** > **Assist me** > **Diagnostics**.

6. **Firewall and Antivirus Settings:**
   - Check firewall or antivirus settings that might block the internet connection.
   - Temporarily disable the firewall to test if the connection is restored.

7. **Ping the Gateway:**
   - Open a terminal (Command Prompt on Windows, Terminal on macOS/Linux) and run `ping [gateway IP]` (e.g., `ping 192.168.1.1`).
   - If successful, it indicates your device can communicate with the router.

8. **Contact ISP:**
   - If all steps fail, contact your Internet Service Provider (ISP) to check if there's an outage in the area or if your service needs attention.

---

## 2. Printer Not Responding

**Symptoms:** Printer is not printing or is stuck in a queue.

**Troubleshooting Guide:**

1. **Check Printer Power and Connections:**
   - Ensure the printer is turned on and properly connected (via USB or Wi-Fi).
   - For network printers, ensure the printer is on the correct Wi-Fi network.

2. **Clear Print Queue:**
   - Cancel all pending print jobs from the device’s print queue.
     - On **Windows**: Go to **Control Panel** > **Devices and Printers** > Right-click on the printer > **See what’s printing**.

3. **Restart Printer:**
   - Power off the printer, wait for 30 seconds, and then power it back on.

4. **Verify Printer Driver:**
   - Check if the printer drivers are correctly installed. If not, download the latest drivers from the printer manufacturer's website.

5. **Test with Another Device:**
   - Try connecting the printer to another computer or device to ensure the issue isn’t specific to the original computer.

6. **Check Printer Settings:**
   - Verify the correct printer is set as the default printer on your device.

7. **Check for Paper Jams:**
   - Open the printer and ensure there are no paper jams in the feed.

8. **Reinstall Printer Drivers:**
   - Uninstall the current printer drivers and reinstall the latest ones. This can solve issues with corrupted or outdated drivers.

---

## 3. Slow Computer Performance

**Symptoms:** Computer is running slowly or freezing frequently.

**Troubleshooting Guide:**

1. **Close Unnecessary Programs:**
   - Open **Task Manager** (Windows) or **Activity Monitor** (Mac) and identify programs that are consuming excessive resources (CPU, memory).
   - Close any unnecessary programs to free up system resources.

2. **Check Disk Space:**
   - Ensure there is enough free space on your hard drive (at least 10-15% free space is ideal).
   - Delete unnecessary files or use **Disk Cleanup** (Windows) or **Disk Utility** (Mac) to remove temporary files.

3. **Restart the Computer:**
   - Restarting the system can clear temporary caches and fix minor software glitches.

4. **Run Malware/Virus Scan:**
   - Use your antivirus software to run a full system scan for malware or viruses that could be slowing down the system.

5. **Update Software:**
   - Outdated software, including OS and drivers, can cause system slowdowns. Ensure that both the OS and all drivers are up to date.

6. **Disable Unnecessary Startup Programs:**
   - Disable unneeded programs from starting up automatically when your computer boots up.
     - On **Windows**: Open **Task Manager** > **Startup**.
     - On **Mac**: **System Preferences** > **Users & Groups** > **Login Items**.

7. **Run Disk Cleanup:**
   - On **Windows**, run **Disk Cleanup** to remove temporary files and system caches.
   - On **Mac**, manually clean system caches by going to the **Library** > **Caches** folder.

8. **Check RAM Usage:**
   - Monitor your computer's RAM usage. If RAM usage is frequently high, consider upgrading your RAM.
     - On **Windows**: Open **Task Manager** > **Performance** > **Memory**.
     - On **Mac**: **Activity Monitor** > **Memory**.

---

## 4. Forgotten Password

**Symptoms:** User cannot access an account due to forgetting the password.

**Troubleshooting Guide:**

1. **Check for Saved Passwords:**
   - Look for saved passwords in your web browser or password manager. Browsers like Chrome, Firefox, and Edge often save credentials for websites.

2. **Use Password Recovery Options:**
   - Use the “Forgot Password” link on the login screen of most services to reset the password via email or SMS.

3. **Verify Account Details:**
   - Ensure that the correct username and email address are being used to reset the password.

4. **Reset via Admin Account:**
   - If you’re on a network (like in a corporate environment), an admin can reset the password for you.

5. **Check for Account Lockouts:**
   - Some systems temporarily lock accounts after several failed login attempts. Wait for 15-30 minutes before trying again, or contact support if the lockout persists.

6. **Enable Two-Factor Authentication (2FA):**
   - Once you regain access to the account, enable 2FA for better security.

---

## 5. System Crashing or Freezing

**Symptoms:** The system freezes or crashes unexpectedly.

### Troubleshooting Guide:

- **Check for System Updates:**
  Install any pending operating system or software updates. Updates often include patches for stability and security.

- **Check for Hardware Failures:**
  Inspect hardware components such as RAM, hard drive, and cooling system. If the computer is overheating, check for dust buildup and clean the fans.

- **Check Event Logs:**
  - In Windows, use the Event Viewer (Windows Key + X > Event Viewer) to look for error logs related to the system crash.
  - On Mac, use the Console app for crash logs.

- **Run System Diagnostics:**
  Use built-in tools like Windows Memory Diagnostic or Apple Diagnostics to test hardware.

- **Disable Hardware Acceleration:**
  Some applications may cause crashes if hardware acceleration is enabled. Try disabling this in your application settings.

- **Perform a Clean Boot:**
  Perform a clean boot to eliminate the possibility that third-party software or startup items are causing system instability.
  - On Windows, go to System Configuration > Services > Disable all non-Microsoft services.

- **Run System File Checker (SFC):**
  For Windows, run `sfc /scannow` in Command Prompt to repair corrupted system files.

- **Check for Memory Leaks:**
  Monitor RAM usage to ensure no application is consuming excessive resources.

---

## 6. Software Not Opening or Crashing

**Symptoms:** A program or application won’t open or crashes immediately after opening.

### Troubleshooting Guide:

- **Restart the Computer:**
  A simple restart can sometimes fix issues with applications not launching.

- **Check for Software Updates:**
  Ensure the application and the OS are up to date. Software developers often release patches to fix bugs.

- **Run as Administrator:**
  Right-click on the program and select "Run as Administrator" to bypass any permission issues.

- **Reinstall the Software:**
  Uninstall the software and reinstall it from the official source to resolve potential corrupted files.

- **Check for Conflicting Software:**
  Disable or uninstall any software that may be conflicting with the application (such as antivirus programs or other security software).

- **Check Application Logs:**
  Review the application logs or Windows Event Viewer for error codes or crashes. This can give clues to the root cause of the issue.

- **Increase Virtual Memory/Page File:**
  For programs that require a lot of memory, increasing the virtual memory or page file size can help.
  - On Windows: `Control Panel > System > Advanced system settings > Settings > Virtual Memory`.

- **Update Graphics Drivers:**
  Ensure that your graphics card drivers are up to date, as outdated drivers can cause graphical applications to crash.

---

## 7. Account Access Issues

**Symptoms:** User cannot access an account due to login problems, such as forgotten passwords, incorrect credentials, or account lockouts.

### Troubleshooting Guide:

- **Check for Saved Credentials:**
  Look for saved passwords in your web browser or password manager. Browsers like Chrome, Firefox, and Edge often store login information for websites, which can be retrieved easily.

- **Use Account Recovery Options:**
  Most services provide a “Forgot Password” or “Account Recovery” link on the login screen. Use this option to reset your password via email or SMS verification.

- **Verify Account Details:**
  Double-check the username and email address you are using. Ensure that there are no typos or errors, especially with email addresses that might contain hidden characters or incorrect domains.

- **Reset via Admin Account:**
  In corporate or networked environments, reach out to the system administrator to reset the password. Admins typically have access to reset user credentials across multiple accounts.

- **Check for Account Lockouts:**
  Many services lock accounts temporarily after multiple failed login attempts to protect against brute force attacks. Wait 15-30 minutes before attempting to log in again, or contact customer support if the lockout persists.

- **Review Security Settings:**
  Some systems may have security settings that require additional verification (e.g., answering security questions or receiving a confirmation code). Ensure all security protocols are correctly followed.

- **Contact Support:**
  If recovery options fail or if you are unable to reset the password, contact the service's customer support for assistance in regaining account access.

- **Enable Two-Factor Authentication (2FA):**
  Once you regain access to the account, enable Two-Factor Authentication (2FA) for added security. This will help protect your account from unauthorized access in the future.

---

## 8. Hardware & Peripheral Troubleshooting

**Symptoms:** Issues with hardware components or peripherals such as printers, keyboards, mice, or external drives not functioning properly.

### Troubleshooting Guide:

- **Check Connections:**
  Ensure that all cables and connectors are securely plugged into the computer and peripherals. If using wireless devices, check the connection and battery levels.

- **Test with Another Device:**
  Test the peripheral device with another computer to determine if the issue is with the device itself or the computer's ports.

- **Update Device Drivers:**
  Outdated or missing drivers can cause peripherals to malfunction. Check the manufacturer's website for the latest drivers and install them.

- **Check for Device Conflicts:**
  In Windows, go to Device Manager to check for any conflicts or warning signs next to the hardware device. Resolve conflicts by updating drivers or uninstalling/reinstalling devices.

- **Run Hardware Diagnostics:**
  Many systems come with built-in diagnostics tools. Run these tools to check for any hardware issues, such as faulty RAM, hard drives, or peripherals.

- **Test with Different Ports:**
  Try plugging the peripheral into a different port to rule out the possibility of a malfunctioning USB, HDMI, or audio port.

- **Check for Power Issues:**
  For powered peripherals (e.g., printers, external hard drives), check that the device is receiving power and turned on. If the device has a power switch, make sure it is in the "on" position.

- **Reset Peripheral Settings:**
  Some peripherals, like printers or networked devices, can have settings reset to default or encounter issues due to configuration changes. Reset the settings as necessary.

- **Replace Faulty Cables:**
  Check cables for signs of wear and tear. Faulty cables can cause connection issues and may need replacing.

- **Contact Manufacturer Support:**
  If the issue persists after trying all troubleshooting steps, contact the peripheral’s manufacturer for support or to inquire about warranty options.
