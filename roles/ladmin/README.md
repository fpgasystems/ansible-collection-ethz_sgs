ladmin
=========

Linux local administrator account as an alternative to root for machines that are managed by ISG (root password is not known). This way administrators can execute commands as root for example using the Virtual Console of the IPMI/BMC/iDRAC.

Requirements
------------

You need the python module `passlib` to be installed on the node that exectues ansible (controller node).

Role Variables
--------------

```yaml
ladmin_password: ""
```
The password of the local admin user. Expects the plain text password. The role will hash the password.

```yaml
ladmin_hashing_salt: "defaulthashsalt"
```
The hashing salt for hashing the password. It is recommended to use a self-chosen salt.

Dependencies
------------

None.

Example Playbook
----------------

It is recommended to store the password and hashing salt in an Ansible Vault.
```yaml
vault_ladmin_password: "secretpassword123"
vault_ladmin_hashing_salt: "randomsalt"
```

```yaml
    - hosts: servers

      roles:
        - role: fpga_systems.ethz_sgs.ladmin
          vars:
            ladmin_password: "{{ vault_ladmin_password }}"
            ladmin_hashing_salt: "{{ vault_ladmin_hashing_salt }}"
```

License
-------

MIT

Author Information
------------------

This role was created in 2025 by [Geert Roks](https://github.com/GeertRoks), maintainer for Heterogeneous Accelerated Compute Cluster (HACC) at the ETH Zürich, Systems Group.
