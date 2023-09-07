# docker_engine

This is a simple Ansible role that installs the Docker Engine on Debian Linux.

## Requirements

This role is very simple. The only requirements are

- Debian Linux
- ansible
- root access on the target host

## Role Variables

All variablea here have default values handled in the ```defaults``` file.

```
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

docker_apt_repo: deb https://download.docker.com/linux/debian bookworm stable

docker_install_packages:
  - docker-ce
  - docker-ce-cli
  - containerd.io
  - docker-buildx-plugin
  - docker-compose-plugin
  ```

## Dependencies

- ansible >= 2.10

## Example Playbook

Just include it in the roles and all set.

    - hosts: docker
      roles:
         - role: docker_engine

## License

MIT

## Author Information

Tamas Molnar - <tmolnar0831@gmail.com> - https://tomsitcafe.com
