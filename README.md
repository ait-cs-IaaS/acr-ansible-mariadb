# MariaDB Role

This role installs and manages MariaDB databases

# Configuration

```
- hosts: db.example.com
  remote_user: "{{ ssh_user }}"
  become: yes
  roles:
    - mariadb
  vars:
    mariadb_users:
      - {
           name: 'horde',
           host: '192.168.1.2',
           password: 'supersecret',
           privileges: 'horde.*:SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,INDEX,ALTER/*.*:SHOW DATABASES'
        }
    mariadb_databases:
      - name: 'horde'

```
