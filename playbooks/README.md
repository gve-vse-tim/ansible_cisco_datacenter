# Reference Playbooks for Cisco Datacenter Collection

## General Requirements

Inventory file which defines the devices, their connection information, and their groupings.

## Switch Configuration

### Export Single Switch Configuration

Required Ansible Variables:
- switch:
  - Ansible string to define switch(es) to be backed up.
  - Example: **fabric3-leaf1** (for a single switch)
  - Example: **fabric3-leaf1:fabric3-leaf2** (for two switches)

### Export Configuration for Entire Fabric

Required Ansible Variables:
- fabrics:
  - Ansible string to define fabric group(s) to be backed up.
  - Example: **fabric3** (for a single fabric)
  - Example: **fabric3:fabric4** (for two fabrics)

### Upload Switch Firmware

Required Ansible Variables:
- switch:
  - Ansible string to define switch(es) to which we will upload.
  - Example: **fabric3-leaf1** (for a single switch)
  - Example: **fabric3-leaf1:fabric3-leaf2** (for two switches)
- firmware:
  - filename of switch firmware located in the subdirectory "./firmware" of the Ansible control workstation
  - Example: **nxos.9.3.10.bin**
  - If not defined, environment variable NXOS_IMG will be used if it exists.  Otherwise, upload will fail.

### Upload Switch Firmware to Whole Fabric

Required Ansible Variables:
- fabrics:
  - Ansible string to define fabric group(s) to be backed up.
  - Example: **fabric3** (for a single fabric)
  - Example: **fabric3:fabric4** (for two fabrics)
- firmware:
  - filename of switch firmware located in the subdirectory "./firmware" of the Ansible control workstation
  - Example: **nxos.9.3.10.bin**
  - If not defined, environment variable NXOS_IMG will be used if it exists.  Otherwise, upload will fail.
