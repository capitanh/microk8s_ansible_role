Microk8s Ansible Role
==================
This role installs microk8s and official helm3 package manager. Two variables are exported for use in the playbook:
* CLUSTER_INFO
* CA_CRT

Requirements
------------
Shell completion and alias are for zsh, no bash config is affected

Role Variables
--------------
Tne variables required by this role are:
```yaml
admin_user:                         # User account to use
```

Dependencies
------------
* pip

Example Playbook
----------------
Register the role in requirements.yml:
```yaml
    - src: capitanh.microk8s_ansible_role
      name: microk8s
```
Include it in your playbooks:
```yaml
    - hosts: servers
      roles:
      - microk8s
```
License
-------
BSD
