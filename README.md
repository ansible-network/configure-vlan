Configure_vlan
----------------------------

Ansible-network user role to configure and manage VLANs where user shall be able to manage the aggregate set of configured VLANs on the network device including being able to create, modify and delete the aggregate set or individual VLANs, over network_cli connection to connect to network device. More info can be found at https://docs.ansible.com/ansible/2.5/network/index.html#network-guide

Requirements
------------

- Ansible 2.5 or later

Dependencies
------------
- None

Example Playbook
----------------

```
---
- hosts: all
  tasks:
    - name: do create_vlan
      import_role:
        name: vlan
        tasks_from: create_vlan
      vars:
        vlans:
          - vlan_id: 106
            name: vlan106
            extensions:
              eos:
                trunk_group: test_trunk_gp
              vyos:
                interfaces: eth1
              iosxr:
                interface_type: GigabitEthernet
                interface_name: 0/0/0/2
```
License
-------

GPL-3.0

Author Information
------------------

Ansible-Networking-Team
