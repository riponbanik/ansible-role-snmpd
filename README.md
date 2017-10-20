# ansible_snmpd
Install and configure snmpd using Ansible. This module is inspired from the work of 
  * https://github.com/sbaerlocher 
  * https://github.com/juju4/ansible-snmpd. 

It allows configuration of version 1, 2c and 3

## Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.4


### Operating systems

Tested with RHEL 6
Targeted for EL and Ubuntu

## Example Playbook

Just include this role in your list.
For example

```
- host: all
  roles:
    - install_snmpd
```

## Variables

```
snmp_auth_key: demo_key
snmp_priv_key: demo_key
community: public
process_list:
  - name: mountd    
  - name: sshd
    min: 1
  - name: crond
    min: 1
    max: 1

```

## Testing SNMP with 1, v2c

snmpwalk -v 1 host_name_or_ip -c public
snmpwalk -v 2c host_name_or_ip -c public

## Testing SNMP with v3
snmpwalk -u snmp -A demo_key -a SHA -x AES -X demo_key -l authPriv host_name_or_ip -v3


