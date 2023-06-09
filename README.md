# Ansible connectivity checker

Simple playbook to test connectivity to a list of IP. 
This can test:
ping

## Ansible Inventory
Use your default Ansible inventory. This file should contain your varibles
```bash
10.10.10.10 snmp_community=public
127.0.0.1 snmp_community=private

[webcheck]
10.10.10.10 snmp_community=public
10.10.10.11 snmp_commuinity=test123

[wmiservers]
10.10.10.11 snmp_commuinity=test123

[sqlcheck]
10.10.10.15

```

```bash
#List tags via:
ansible-playbook -I <inventory-file> test_connectivity.yaml --list-tags
```

## Usage:
```python
#List tags via:
ansible-playbook -I <inventory-file> test_connectivity.yaml --list-tags

# Run with defaults
ansible-playbook -I <inventory-file> test_connectivity.yaml

# Verbose
ansible-playbook -I <inventory-file> test_connectivity.yaml -vvvv

# returns 'geese'
ansible-playbook -I <inventory-file> test_connectivity.yaml --tags ping

```

## Copyright

[RyanGillan.com](http://www.ryangillan.com/)
