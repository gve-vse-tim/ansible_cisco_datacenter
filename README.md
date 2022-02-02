# ansible_cisco_datacenter

An Ansible collection of roles and useful playbooks developed to automate
our (Cisco GVE) lab environment.

## Requirements
- Python 3.8.x
- Ansible Core 2.11.x
- Ansible 4.2.x
- Paramiko 2.7.2
- UCSM SDK 0.9.10

## Instructions

### Pre-Requisities

Python virtual environment:

```bash
virtualenv ansible-4.2
source ansible-4.2/bin/activate
pip install -r requirements.txt
```

Install the latest version of this collection from GitHub

```bash
# Enable any http_proxy or https_proxy environment variables needed
ansible-galaxy collection install git+https://github.com/gve-vse-tim/ansible_cisco_datacenter
```

Create an inventory file for your infrastructure

### Playbooks

Running the collection's playbooks directly:

```bash
# TODO
```

## Other related Ansible content

- [Using Collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html)
- [Collection Directory Structure](https://docs.ansible.com/ansible/latest/dev_guide/developing_collections_structure.html)
- [Ansible Collection for UCS Modules](https://github.com/CiscoDevNet/ansible-ucs)
- [Ansible UCS Roles](https://github.com/CiscoUcs/ansible-role-ucs)
