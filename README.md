# Ansible Role: Create a new mysql database and user using PLESK API
Creates a new database user and database in [Plesk](https://docs.plesk.com/en-US/onyx/api-rpc/reference/managing-databases/creating-database-users.34472/).

## Requirements
No special requirements:
  * a server running plesk
  * this role requires admin access for plesk
  
## Role Variables
Required variables are listed below and can be set with values (see `vars/main.yml`):
```yaml
host_url: <your-strato-server-id>.stratoserver.net
host_port: 8443

dbname: "dbmydomain"
dbuser: "dbuser"
dbpw: "secure-db-pw"

plesk_admin_user: "admin"
plesk_admin_pw: "secure-admin-pw"
```

Available variables are listed below, along with default values (see `defaults/main.yml`):
```yaml
webspace_id: 1
dbtype: "mysql"
```

## Dependencies
None.

## Example Playbook
```yaml
- hosts: strato-server
  become: yes
  vars_files:
    - vars/main.yml
  roles:
    - { role: ansible.role.create-mysqldb-and-user-using-plesk-api }
```
Inside `vars/main.yml`:
```yaml
host_url: <your-strato-server-id>.stratoserver.net
host_port: 8443

dbname: "dbmydomain"
dbuser: "dbuser"
dbpw: "secure-db-pw"

plesk_admin_user: "admin"
plesk_admin_pw: "secure-admin-pw"
```

## Authors
This role was created in 2018 by Sergej Kukshausen and Susann Sgorzaly.


