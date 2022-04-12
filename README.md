[![CI](https://github.com/kirill-zak/ansible-dockovpn-openvpn-docker/actions/workflows/ci.yml/badge.svg)](https://github.com/kirill-zak/ansible-dockovpn-openvpn-docker/actions/workflows/ci.yml)
[![Release](https://github.com/kirill-zak/ansible-dockovpn-openvpn-docker/actions/workflows/release.yml/badge.svg)](https://github.com/kirill-zak/ansible-dockovpn-openvpn-docker/actions/workflows/release.yml)

dockovpn_openvpn_docker
=========

 OpenVPN in a Docker container

## Support distributive

* CentOS 8
* Debian 10 (Buster)
* Debian 11 (Bullseye)
* Fedora 35
* Ubuntu 18.04 (Bionic Beaver)
* Ubuntu 20.04 (Focal Fossa)

Requirements
------------

Docker engine

Role Variables
--------------

- `dockovpn_openvpn_docker_container_name`: Name of container
- `dockovpn_openvpn_docker_container_volume`: Name of container volume
- `dockovpn_openvpn_docker_host_ip`: Host IP
- `dockovpn_openvpn_docker_configuration_port`: Port for get configuration
- `dockovpn_openvpn_docker_log_driver`: Logger driver. Default value is `none` for disable log. List of available logger drivers # https://docs.docker.com/config/containers/logging/configure/#supported-logging-drivers
- `dockovpn_openvpn_docker_tag` Tag found at # https://hub.docker.com/r/alekslitvinenk/openvpn/tags

Dependencies
------------

- Docker

Example Playbook
----------------

    - name: Install OpenVPN
      hosts: openvpn
      become: true
      vars:
        dockovpn_openvpn_docker_host_ip: 192.168.0.1
      roles:
        - role: kirill_zak.ansible_docker
        - role: kirill_zak.dockovpn_openvpn_docker

License
-------

GPL-2.0

Author Information
------------------

https://kirill-zak.ru
