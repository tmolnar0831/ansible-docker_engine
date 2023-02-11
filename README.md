docker_engine
=========

A simple Ansible role that installs the Docker Engine on Debian Linux

Requirements
------------

This role tries to be as simple as it is possible. The only requirement is an installed Ansible to use it.

Role Variables
--------------

Every variable here has default values handled in the "defaults". The role is written for Debian Bullseye.

docker_remove:
  - docker_engine
  - docker
  - docker.io
  - containerd
  - runc

docker_prerquisites:
  - ca-certificates
  - gnupg

docker_gpg_url: https://download.docker.com/linux/debian/gpg

docker_apt_repo: deb https://download.docker.com/linux/debian bullseye stable

docker_install_packages:
  - docker-ce
  - docker-ce-cli
  - containerd.io
  - docker-buildx-plugin
  - docker-compose-plugin

Dependencies
------------

This role tries to be as simple as it is possible. The only requirement is an installed Ansible to use it.

Example Playbook
----------------

Just include it in the roles and all set.

    - hosts: all
      roles:
         - role: docker_engine

License
-------

MIT

Author Information
------------------

Tamas Molnar - <tmolnar0831@gmail.com> - https://tomsitcafe.com
