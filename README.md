Ansible Role: ansible-role-wordpress
=========

This Ansible playbook will Deploy & run Docker Compose project for WordPress instance. It will also configure Let's Encrypt certificates for specified domain. It consists of 3 separate containers running:
* WordPress
* Nginx (enabled with Let's Encrypt HTTPS encryption)
* MySQL



Role Variables
--------------

This role comes with following variables defined in defaults/main.yml:

```
system_user: ubuntu
compose_project_dir: /home/{{ system_user }}/compose-wordpress
domain: foolcontrol.org
stage: staging
wp_version: 5.2.4
wp_db_user: admin
wp_db_psw: change-M3
db_root_psw: change-M3
wp_db_name: wordpress
wp_db_tb_pre: wp_
wp_db_host: mysql
```

If role is run without changing these, WordPress instance with Nginx virtual host as well as Database settings will be setup with these values. 



Dependencies
------------

**ToDo:**
Determine if "AdnanHodzic.docker-compose-setup" role should be set as role dependency. If yes, update this section of ReadMe + meta code.

Example Playbook
----------------

```
- hosts: servers
  remote_user: "{{ system_user }}"
  roles:
    - { role: ansible-role-wordpress }}  
```

License
-------

GPLv3
