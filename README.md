# ansible_snmpd
Install and configure snmpd using Ansible

# This module is inspired from the work of https://github.com/sbaerlocher and https://github.com/juju4/ansible-snmpd. 

It allows configuration of version 1,2c and 3

# Testing SNMP with 1, v2c

snmpwalk -v 1 host_name_or_ip -c public
snmpwalk -v 2c host_name_or_ip -c public

# Testing SNMP with v3
snmpwalk -u snmp -A demo_key -a SHA -x AES -X demo_key -l authPriv host_name_or_ip -v3


