Systemd mount remote NFS storage
=========

This role mount NFS storage with systemd unit.

Role Variables
--------------

* `nfs_server` - IP address or FQDN name of systemd unit
* `nfs_export` - NFS export directory name
* `mount_base_path` - base path in local filesystem for mount NFS storage (default: /mnt/nfs)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- name: Automount remote NFS storage with systemd
  hosts: all
  roles:
    - { role: systemd_mount_remote_nfs_storage, nfs_server: "0.0.0.1", nfs_export: "/nfs_export_dir" }

```

Including an example of how to use your role (for instance, without variables passed in as parameters) is always nice for users too:

```
- name: Automount remote NFS storage with systemd
  hosts: all
  roles:
    - { role: systemd_mount_remote_nfs_storage }

```

License
-------

GPLv3

Author Information
------------------

Maxim Ishchenko <m.g.ishchenko@yandex.ru>
