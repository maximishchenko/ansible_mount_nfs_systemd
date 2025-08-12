# Ansible PostgreSQL for 1C from Postgres Professional installation

Playbook

- Validate required variables, such as `postgres_password` and `app_1c_password`
- Check if pgpro specific version repository exists
- Remove old repository file if exists
- Add repository for specific PostgreSQL version (`postgresql_1c_version` variable)
- Install PostgreSQL
- Set password for postgres user
- Create user for 1C application (`app_1c_user` variable)
- Set password for user of 1C application (`app_1c_password` varable)
- Grant permission for user of 1C application

## Preparation

1. Add servers IP or FQDN to inventory file such as ```inventory/inventory.cfg```

> Example [inventory/inventory.ini.sample](inventory/inventory.ini.sample))

2. Add variables to host_vars or group_vars

> Example [host_vars/0.0.0.1/](host_vars/0.0.0.1))

## Usage

1. Run with ```Makefile```:

```shell
make setup
```

or your can pass path to inventory file with environment variable

```shell
make setup INVENTORY=inventory/my_inventory_file.cfg
```

2. Run Ansible Playbook directly

```shell
ansible-playbook -i inventory/inventory.cfg install_1c_postgres_pro.yml
