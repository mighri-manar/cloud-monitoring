# VMs Directory - README

This directory contains all virtual machine files related to the project/lab environment. Below is a clear description of the main items you may find here.

## Contents

### 1. **VM Configuration Files (.vmx)**
VMware virtual machine configuration files. These contain hardware settings, network modes, shared folders, and internal VM properties. **These files should NOT be shared publicly** because they may include host paths or identifiers.

### 2. **Virtual Disk Files (.vmdk)**
The virtual hard drives used by each VM. Often large in size. These files store the actual OS data, applications, and user files.

### 3. **Snapshots Directory**
Contains snapshot data, including memory and disk delta files. Enables rollback to previous VM states.

### 4. **Logs (.log)**
VMware log files documenting VM boot, hardware emulation, and network configuration. Useful for debugging issues such as boot failures or network misconfigurations.

### 5. **NVRAM Files (.nvram)**
Store the VM's BIOS/EFI configuration. Normally small and rarely edited.

### 6. **Other Supporting Files**
- **.vmxf** — Team configuration metadata (optional)
- **.lck directories** — Lock files created when a VM is running
- **metadata.json** or other generated metadata (depending on platform)

## Notes
- Avoid uploading `.vmx`, `.log`, or `.lck` files publicly.
- Use snapshots responsibly to save disk space.
- Maintain a clean directory structure to avoid VM corruption.

If needed, additional documentation for each VM (purpose, OS, credentials, network role) can be added below.

---
*Last updated: <!-- date here -->*

