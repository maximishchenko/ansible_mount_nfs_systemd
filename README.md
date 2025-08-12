# Ansible Mount NFS storage with systemd automount unit

Playbook

- Install NFS Client
- Generate mount entrypoint name, mount unit name and automount unit name
- Create mount entrypoint if not exists
- Create mount and automount systemd units

## Preparation

1. Add servers IP or FQDN to inventory file such as ```inventory/inventory.yml```

> Example [inventory/inventory.sample.yml](inventory/inventory.sample.yml))

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
ansible-playbook -i inventory/inventory.cfg nfs_storage_automount.yml
