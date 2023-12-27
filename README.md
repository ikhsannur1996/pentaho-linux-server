# Installation Guide: Pentaho on Linux

## Introduction
This guide provides detailed steps to install Pentaho Data Integration (PDI) on a Linux system. Pentaho is a powerful data integration and business analytics tool.

## Prerequisites
- Linux distribution (e.g., Ubuntu)
- Minimum 8GB RAM and 20GB available hard disk space
- Access to a Linux machine meeting hardware requirements
- Internet connectivity

## Steps

### 1. Update Package Lists
```bash
sudo apt-get update
```

### 2. Install XFCE Desktop Environment (Optional)
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

### 6. Enable RDP Port (Default is 3389)
Ensure port 3389 for RDP is open in the firewall settings if needed.

### 7. Check XRDP Status and Port Status
```bash
sudo systemctl status xrdp
sudo netstat -tuln | grep 3389
```

### 8. Set Root Password (if necessary)
```bash
sudo passwd root
```

### 9. Create User for Remote Access
```bash
sudo adduser admin
sudo usermod -aG sudo admin
sudo passwd admin
```
Set the desired password for the "admin" user.

### 10. Remote Desktop Login from Windows
Access the Linux desktop using Remote Desktop Connection on Windows.

### 11. Download and Install Pentaho Data Integration (PDI)
- Visit the Pentaho website or PDI source.
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
```
