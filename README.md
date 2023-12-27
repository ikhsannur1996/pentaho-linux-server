# Installation Guide: Pentaho Data Integration on Linux

## Introduction
This guide provides detailed steps to install Pentaho Data Integration (PDI) on a Linux system. Pentaho is a powerful data integration and business analytics tool.

## Prerequisites
- Linux distribution (e.g., Ubuntu)
- Minimum 8GB RAM and 20GB available hard disk space
- Access to a Linux machine meeting hardware requirements
- Internet connectivity

## Why Use XFCE GUI?
For this installation, we recommend using the XFCE desktop environment. XFCE is chosen due to its lightweight nature, offering a balance between resource efficiency and a complete desktop experience. Here's why XFCE is advantageous:
- **Lightweight:** XFCE requires fewer system resources, making it ideal for systems with limited RAM or processing power.
- **Complete Desktop:** Despite being lightweight, XFCE provides a complete and user-friendly desktop experience, enabling efficient navigation and usability.
- **Customizability:** XFCE allows for extensive customization, allowing users to tailor their desktop environment according to their preferences.

By opting for XFCE, users can ensure a smooth and responsive experience while working with Pentaho Data Integration.

## Steps for Ubuntu or Debian Distributions

### 1. Update Package Lists
```bash
sudo apt-get update
```

### 2. Install XFCE Desktop Environment
```bash
sudo apt-get install xfce4-session xfce4-goodies xfce4-panel
```

### 3. Install XRDP for Remote Desktop Access
```bash
sudo apt-get install xrdp
```

### 4. Install Default Java Development Kit (JDK)
```bash
sudo apt install default-jdk
```

### 5. Install Firefox (Optional)
```bash
sudo apt-get install firefox
```
**Note:** Ensure a web browser is available on your Linux machine to download Pentaho Data Integration, drivers, and any required dependencies.

### 6. Enable RDP Port (Default is 3389)
Ensure port 3389 for RDP is open in the firewall settings if needed.

### 7. Check XRDP Status and Port Status
```bash
sudo systemctl status xrdp
sudo netstat -tuln | grep 3389
```

### 8. Set Root Password
```bash
sudo passwd root
```
**Note:** Sometimes, a root password might be required for initial GUI initialization.

### 9. Create User for Remote Access
```bash
sudo adduser user1
sudo usermod -aG sudo user1
sudo passwd password1
```
Set the desired password for the "user1" user.

### 10. Remote Desktop Login from Windows
[Connecting to Linux Remote Desktop from Windows using RDP Guide](#Connecting-to-Linux-Remote-Desktop-from-Windows-using-RDP)

### 11. Download and Install Pentaho Data Integration (PDI)
- [Complete Guide](https://github.com/ikhsannur1996/pentaho)
- Visit the Pentaho website or PDI source. Go to the official Pentaho website: https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html.
- Download the Pentaho Data Integration archive.

### 12. Extract and Run Spoon.sh
```bash
tar -zxvf <file_name.tar.gz>
cd <extracted_folder_name>
./spoon.sh
```
Replace `<file_name.tar.gz>` and `<extracted_folder_name>` with actual file and folder names.

## Notes
- Ensure your Linux system meets minimum hardware requirements for smooth operation.
- Adjustments might be required for different Linux distributions.
- Safeguard root and user passwords for security reasons.


## Steps for Red Hat-Based Distributions

### 1. Update Package Lists
```bash
sudo yum update   # For CentOS 6 and earlier
```
or
```bash
sudo yum update   # For CentOS 7 and later
```
### 2. Install XFCE Desktop Environment
```bash
sudo yum install epel-release -y
sudo yum groupinstall "X Window system" -y
sudo yum groupinstall "Xfce" -y
```
### 3. Install XRDP for Remote Desktop Access
```bash
sudo yum install xrdp
```

### 4. Install Default Java Development Kit (JDK)
```bash
sudo yum install java-1.8.0-openjdk   # For Java 8
```
or for Java 11:
```bash
sudo yum install java-11-openjdk-devel   # For Java 11
```

### 5. Install Firefox (Optional)
```bash
sudo yum install firefox
```

### 6. Enable RDP Port (Default is 3389)
Ensure port 3389 for RDP is open in the firewall settings if needed.

### 7. Check XRDP Status and Port Status
```bash
sudo systemctl status xrdp
sudo ss -tuln | grep 3389
```

### 8. Set Root Password
```bash
sudo passwd root
```
**Note:** Sometimes, a root password might be required for initial GUI initialization.

### 9. Create User for Remote Access
```bash
sudo adduser user1
sudo usermod -aG wheel user1   # For sudo access
sudo passwd password1
```
Set the desired password for the "user1" user.

### 10. Remote Desktop Login from Windows
[Connecting to Linux Remote Desktop from Windows using RDP Guide](#Connecting-to-Linux-Remote-Desktop-from-Windows-using-RDP)

### 11. Download and Install Pentaho Data Integration (PDI)
Refer to the Pentaho website or PDI source for downloading and installing PDI. Adjust commands based on the distribution.

### 12. Extract and Run Spoon.sh
```bash
tar -zxvf <file_name.tar.gz>
cd <extracted_folder_name>
./spoon.sh
```
Replace `<file_name.tar.gz>` and `<extracted_folder_name>` with actual file and folder names.

### Notes
- Adapt commands as needed for specific Red Hat-based distributions (CentOS, Fedora).
- Ensure the system meets the minimum hardware requirements for smooth operation.
- Remember to secure passwords for root and users for security reasons.

# Connecting to Linux Remote Desktop from Windows using RDP

## Steps to Connect

1. **Open Remote Desktop Connection:**
   - Press `Windows Key + R` to open the Run dialog box.
   - Type `mstsc` and hit Enter to open Remote Desktop Connection.

2. **Enter Linux Machine's IP Address and Port (if not default):**
   - In the Remote Desktop Connection window, enter the IP address of your Linux machine, followed by a colon and the port number (if the RDP port is not the default 3389).
   - Example: `192.168.1.100:3390`

3. **Enter Credentials:**
   - Enter the username and password created on the Linux machine (e.g., "admin" with the set password).

4. **Authenticate and Connect:**
   - Click "OK" or "Connect" to initiate the connection.
   - Accept any certificate warnings that may appear during the connection process.

5. **Remote Desktop Session:**
   - After authentication, a new window will display the Linux desktop environment (e.g., XFCE or your configured desktop).

6. **Usage:**
   - Interact with the Linux desktop remotely as if you were using the machine directly.

7. **Disconnecting:**
   - To end the remote session, close the Remote Desktop Connection window or use the session window's close button.
  
## Visual Guide
- For a visual guide, watch this [Connecting to Linux Remote Desktop from Windows using RDP](https://youtu.be/oiNStSYwJv4)

## Note
- Ensure the Linux machine's XRDP service is running and the RDP port is correctly specified in the connection address.
- Adjust the username, password, IP address, and port based on your specific configurations.
- This guide assumes a working XRDP setup on the Linux machine and a standard Remote Desktop Connection utility on the Windows system.

![Screenshot (116)](https://github.com/ikhsannur1996/pentaho-linux-server/assets/32507742/94c3c78d-3df8-481a-bc31-bc577e87fd39)


