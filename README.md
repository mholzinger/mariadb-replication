# MariaDB Cluster (Ansible playbook for Vagrant)

This Ansible playbook follows steps outlined in the official MariaDB documentation for enabling a Primary and Secondary MariaDB SQL server.

Steps followed (and sample passwords used) linked here:

https://mariadb.com/kb/en/setting-up-a-replication-slave-with-mariabackup/

This playbook establishes:
- Two 1GB Centos 8 nodes
- Installs the latest versions of MariaDB and Keepalived for cluster orchestration.
- fqdn = primary / ip = 192.168.40.2
- fqdn = secondary / ip = 192.168.40.2
- Innodb Storage engine / Binary logging
- Full replication from primary to secondary node

Requirements for playbook to run:
- Vagrant
- VirtualBox
- Ansible

TODO Items for this playbook:
- Use Ansible Set Master/Slave commands instead of using .sql commands
- Add test cases to show replicated data
- Enable Keepalived failover testing

Further Ansible MySQL (MariaDB) replication Documentation below:
https://docs.ansible.com/ansible/latest/modules/mysql_replication_module.html#mysql-replication-module
