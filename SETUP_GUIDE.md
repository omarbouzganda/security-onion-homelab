# Security Onion Setup Guide

## Prerequisites
- **System Requirements**: Ensure that your system meets the following minimum requirements:
  - 8 GB RAM (16 GB or more recommended)
  - 2 CPUs (4 CPUs or more recommended)
  - At least 20 GB of disk space for installation (more for storage)
  - Internet connection for downloading packages.

- **Software Requirements**:
  - VMware Workstation Pro or VMware Player
y  - ISO file for Security Onion

## VMware Configuration
1. **Install VMware Workstation Pro** or Player on your host machine.
2. **Create a new Virtual Machine**:
   - Select `Typical` configuration.
   - Choose to install the operating system from an ISO file and select the Security Onion ISO.
3. **Configure VM Settings**:
   - Allocate `4 GB RAM`.
   - Select at least `2 CPUs`.
   - Configure the network adapter:
     - Use Bridged or NAT based on your requirement.
   - Enable virtualization support if available in BIOS.

## Security Onion Installation
1. Start the VM and follow the installation instructions:
   - Select `Install Security Onion`.
   - Accept the terms and choose the appropriate options for your network configuration.
2. Configure the system during installation:
   - Set your hostname and basic settings.
   - Choose the network interface for monitoring.
3. Complete the installation and reboot the system.

## Network Setup
- **Confirm Network Interfaces**: After installation, check available network interfaces using:
  ```bash
  ip a
  ```
- **Configure Static IP**: Edit the configuration file to set up static IP for management interface:
  ```bash
  sudo nano /etc/network/interfaces
  ```
  - Add the required configurations following the format.

## Web UI Access
1. Open a web browser and enter the IP address of your Security Onion instance followed by `443` or `80` (e.g., https://192.168.x.x).
2. Log in with your credentials.

## Test VM Creation
1. In your VMware setup, create a new VM for generating test alerts:
   - Install any common operating system (e.g., Ubuntu).
2. Within this VM, you can run tools or scripts to generate alerts for Security Onion to monitor.

## Alert Generation
- Use tools like `Metasploit`, `nmap`, or custom scripts from your test VM to generate traffic that creates alerts in Security Onion.

## Verification Checklist
- **After setup, ensure the following**:
  - Security Onion services are running properly:
    ```bash
    sudo sosutil status
    ```
  - You can view alerts on the web UI.
  - Test alerts are generated successfully from the test VM.
  - Review logs and ensure data is being correctly captured.

**Note**: Document any issues or adjustments you make during your configuration for future reference and troubleshooting.
