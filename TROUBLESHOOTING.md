# Troubleshooting Guide

## Common Issues and Solutions

### 1. Unable to Connect to Security Onion
- **Check Network Configuration**: Ensure that your network settings are correctly configured. 
- **Verify Service Status**: Use the following command:
  ```bash
  sudo so-status
  ```
- **Firewall Rules**: Check that your firewall settings allow connections.

### 2. Performance Issues
- **Resource Utilization**: Check CPU and Memory usage with:
  ```bash
  top
  ```
- **Log Size**: Large logs can slow down the system. Consider rotating or cleaning old logs.

### 3. Update Problems
- **Repository Access**: Ensure that the repository is reachable and that you have the right permissions.
- **Command**: Use this command to update:
  ```bash
  sudo apt-get update && sudo apt-get upgrade
  ```

### 4. Alerts Not Triggering
- **Configuration Files**: Check your configuration files for any misconfigurations.
- **Service Status**: Ensure that relevant services are running:
  ```bash
  sudo so-status -s
  ```

### 5. Snapshot Restore Failures
- **Correct Snapshot Time**: Ensure you are trying to restore from the correct snapshot.
- **Disk Space**: Ensure there is enough disk space available to perform restore operations.

### 6. General Trouble Shooting Commands
- For system logs:
  ```bash
  less /var/log/syslog
  ```
- For current services status:
  ```bash
  sudo so-status
  ```

## Seeking Help
If issues persist, consider reaching out to the Security Onion community or forums for support.