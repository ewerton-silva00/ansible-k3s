k3s
=========

Ansible Role to install Lightweight Kubernetes (k3s).

Role Variables
--------------

```
---
# K3s version (kubernetes version)
# See: https://github.com/k3s-io/k3s/releases
k3s_release_version: 1.19.16

# Directory to hold state. Defaults to '/var/lib/rancher/k3s'
k3s_server_data_dir: ''

# Do not deploy packaged components and delete any deployed components (valid items: coredns, servicelb, traefik,local-storage, metrics-server)
k3s_server_disable_services: []

# Default local storage path for local provisioner storage class. Defaults to '/var/lib/rancher/k3s/storage'
k3s_server_local_storage_path: ''

# Node labels
k3s_server_node_labels: []
```

Example Playbook
----------------

```yaml
- name: Ansible Playbook to install and configure Lightweight Kubernetes (k3s)
  hosts: all
  gather_facts: yes
  any_errors_fatal: true
  become: true
  roles:
    - role: k3s
      tags:
        - k3s
```

License
-------

MIT

Author Information
------------------

Ewerton Silva <ewerton116@gmail.com>
