Microk8s Ansible Role
==================
This role installs microk8s kubernetes distribution. The following services are enabled by default:
* dns
* storage
* ingress
* host-access

You can select the enabled services by listing then in microk8s_services variable.

A few other tools are also installed:
* k9s
* helm
* vclusters

Requirements
------------
Shell completion and alias are for zsh, no bash config is affected

Role Variables
--------------
The variables for this role are:
```yaml
channel: latest           # Which snap channel to use when installing microk8s, defaults to latest
helm_channel: latest/stable  # Which snap channel to use when installing helm, defaults to stable
helm_diff_url: "https://github.com/databus23/helm-diff"  # Helm Diff plugin source
helm_diff_version: "v3.12.5"  # Helm Diff plugin version to install
admin_user:        # User account to use
microk8s_services: # Default list of services to enable
  - dns
  - storage
  - ingress
  - host-access
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
