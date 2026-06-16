NVIDIA CUDA
=================

Install the driver for NVIDIA GPUs and the CUDA toolkit. Supports both the open and proprietary drivers.

Requirements
------------

None.

Role Variables
--------------

```yaml
cuda_driver_version: ""
```
Branch version of the driver. Only provide the major branch version.

```yaml
cuda_driver_use_proprietary: true
```
Boolean indicating to use the Proprietary drivers (`true`) or the open-source drivers (`false`).

```yaml
cuda_driver_cuda_keyring_version: "1.1-1"
```
The version of the `cuda-keyring` package. This package installs the gpg keyring for network installs of nvidia software using apt. The version will stay the same for a long time, so it is pretty safe to keep it at the default.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
```

License
-------

MIT

Author Information
------------------

This role was created in 2026 by [Geert Roks](https://github.com/GeertRoks), maintainer for Heterogeneous Accelerated Compute Cluster (HACC) at the ETH Zürich, Systems Group.
