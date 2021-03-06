# Overview

This project provides Ansible playbooks for setting up the social enterprise directory. It assumes install on an Ubuntu server.

# Preparing Ansible

On your controller machine:

1. Install ansible
2. Install role dependencies required for social enterprise directory

  `ansible-galaxy install -r role_dependencies.yml`
  
3. Set `allow_world_readable_tmpfiles=true` in ansible.cfg

# Configure hosts

Using the `hosts` file provided in this repo as an example, setup your local ansible hosts file at `/etc/ansible/hosts`

* [backend_servers] : list the servers you want to use as backend for social enterprise directory
* [frontend_servers] : list the servers you want to use as frontend for social enterprise directory

# Executing Playbooks

To create backend servers for the social enterprise directory, use the following playbook:

  `ansible-playbook playbooks/se-dir-backend-playbook.yml`


To create frontend servers for the social enterprise directory, use the following playbook:

  `ansible-playbook playbooks/se-dir-frontend-playbook.yml`

# Executing Playbook on Remote hosts

To execute a playbook on remote host as a user with sudo privileges:

  `ansible-playbook <playbook> --become -u <username> --ask-become-pass --ask-pass`
