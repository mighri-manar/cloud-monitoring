# VMs Directory README

## Overview
This directory contains the virtual machines used in our lab setup.

### Asterisk VM
- **OS:** Debian 12
- **Services Installed:**
  - FTP (vsftpd)
  - HTTP (nginx)
  - Syslog

### Radius VM
- **OS:** Debian 12
- **Services Installed:**
  - FreeRADIUS

### Client VM

- **OS**: Debian 12

- **Services Installed**: None by default

- **Purpose**: Acts as a client for testing access to services on Asterisk and Radius VMs.

## Notes
- These VMs are configured to support lab experiments including service access control, ACL testing, and network monitoring.
- Configuration files for the services are included in each VM's directory for reference or backup purposes.
- Ensure correct permissions when accessing configuration files (some require `sudo`).

