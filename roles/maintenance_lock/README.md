Maintenance Lock
================

Systemd based lockout of users for maintenance window enforcement.

Requirements
------------

None.

Role Variables
--------------

```yaml
maintenance_lock_message: ""
```
Message that is shown when users try to login during the maintenance window and they get denied access. The message has an automatic generic header with the start and stop time of the maintenance window.

```yaml
maintenance_lock_start_time: ""
maintenance_lock_stop_time: ""
```
The start and stop time of the maintenance window. Use the format: "YYYY-MM-DD hh:mm"

```yaml
maintenance_lock_delay: 60
```
The delay after the start time after which all user sessions except for root are terminated.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
        - role: fpga_systems.ethz_sgs.maintenance_lock
          vars:
            maintenance_lock_start_time: "2026-02-14 01:00"
            maintenance_lock_stop_time: "2026-02-15 20:45"
            maintenance_lock_message: |
              Maintenance in progress
              You will not be able to login during this period.

              Please try again after the maintenance period is over.
              Apologies for any inconveniences.
```

License
-------

MIT

Author Information
------------------

This role was created in 2026 by [Geert Roks](https://github.com/GeertRoks), maintainer for Heterogeneous Accelerated Compute Cluster (HACC) at the ETH Zürich, Systems Group.
