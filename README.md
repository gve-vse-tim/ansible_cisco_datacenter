# ansible_cisco_datacenter

An Ansible collection of roles and useful playbooks developed to automate
our (Cisco GVE) lab environment.

## Requirements
- Python 3.10.x
- Pip 22.0.3
- Ansible 5.3.0 (implies Ansible Core 2.12.2)
- Paramiko 2.9.2
- UCSM SDK 0.9.12

## Instructions

### Pre-Requisities

Python virtual environment:

```bash
python -m venv ansible-5.3
source ansible-5.3/bin/activate
pip install -r requirements.txt
ansible-galaxy collection install -r requirements.yml
```

### Inventory

For reasons that are not 100% clear to me, the inventory and variables
directory structure behave differently than your typical playbook repository
when I first started developing this (circa Ansible 2.9/2.10). I haven't
attempted to see if it works any differently lately.

As such, the host_vars and group_vars directories need to be embedded within
the inventory directory and not be separate from tree.  For example:

```
parent_playbook_directory:
    inventory:
        global:
            hosts.yaml - The complete host inventory for all managed devices
        core_infrastructure:
            hosts.yaml - remapping of those global/hosts to collection group names
        group_vars:
            all.yaml - vars for all devices
            upstream_switches.yaml - vars for the upstream_switches group
        host_vars:
            switch-a.yaml - vars for switch-a
```

In trying to have the traditional, separated directory structure, namely:

```
parent_playbook_directory:
    inventory:
        global:
            hosts.yaml - The complete host inventory for all managed devices
        core_infrastructure:
            hosts.yaml - remapping of those global/hosts to collection group names
    group_vars:
        all.yaml - vars for all devices
        upstream_switches.yaml - vars for the upstream_switches group
    host_vars:
        switch-a.yaml - vars for switch-a
```

The variables were not getting mapped to the correct hosts. I couldn't easily
decipher if this was do to my group remapping or the use of a collection. APFADD(tm)

The **__requirements__** for this collection are to have the various device groups
defined in your inventory YAML:

- upstream_switches: switches that will need the VLANs configured on them
- gateway_switches: switches that will ned SVIs and HSRP configured on them

Additionally, you'll need to build the relevant group_vars and host_vars for the
settings of each role.

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
