# Ansible-Role: MariaDB

This role installs and manages [MariaDB](https://mariadb.org/) databases

## Requirements

- Debian or Ubuntu (18.04 or newer)

## Example Playbook

```yaml
- hosts: db.example.com
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

## License

GPL-3.0
