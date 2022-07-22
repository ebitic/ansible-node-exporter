# Ansible playbook for Prometheus node exporter

Ansible playbook for deploying Prometheus node exporter agent.

## Ansible requirement

Before launching the playbook, you need to configure :
- user used by ansible on the remote server
- node exporter version
- hosts in the /etc/ansible/hosts

**ansible-node-exporter.yml**
```
---
- name: Install Prometheus node exporter
  hosts: node-exporter-client
  remote_user: <Your user>
  become: yes
  vars:
    node_exporter_version: <node exporter version>
```

In my case, i'm using an ssh key between my ansible server and the remote server.

Now, you can run it
```
ansible-playbook ansible-node-exporter.yml --ask-become-pass
```

---

Developed by Evan Bitic
