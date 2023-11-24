sleif.letsencrypt_nginx_docker
============

This role runs a nginx based letsencrypt stack on docker.

Requirements
------------

Use it on a machine setup with ansible role sleif.docker.

Role Variables
--------------
- container_storage_dir_base (/srv)
- nameserver_fallback_needed (true, in case you want local network independed DNS, example pihole on same docker host)
- docker_network_name (can be defined in sleif.docker)

Dependencies
------------

Needs geerlingguy.docker to make sure Docker is available.
Needs sleif.docker to make sure Docker is configured as needed.

Example Playbook
----------------

    - hosts: "server"
      user: root
      vars:
        docker_network_name: 'custom_docker_network'
      roles:
        - { role: sleif.letsencrypt_nginx_docker, tags: "letsencrypt_nginx_docker" }

License
-------

MIT

Author Information
------------------

Created in 2021 by Sebastian Berthold
