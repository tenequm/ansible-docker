Ansible Role: Docker
=========
This role applies Docker with docker-compose installation (it also deletes previous version if it is installed) for Ubuntu/Debian and disables docker changes for iptables.

Requirements
------------
This role requires only root access for accomplishing its operations, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:
```
- hosts: localhost
  become: yes
  roles:
    - role: tenequm.docker
```

Role Variables
--------------
Docker-compose bin file path (default '/usr/local/bin/docker-compose'):
```
docker_compose_path: /usr/local/bin/docker-compose
```
Docker-compose version (default '1.17.1'):
```
docker_compose_version: "1.17.1"
```

Example Playbook
----------------
```
- hosts: localhost
  become: yes
  roles:
    - { role: tenequm.docker }
```
License
-------
MIT

Author Information
------------------
This role was created in 2017 by [Mykhaylo Kolesnik](http://github.com/tenequm).
