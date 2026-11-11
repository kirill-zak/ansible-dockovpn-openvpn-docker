dockovpn_openvpn_docker
=========

Setup and run the Dockovpn OpenVPN server in a Docker container

## Support distributive

* AlmaLinux `8.x` (`8.5` – `8.10`), `9.x` (`9.0` – `9.8`)
* Alpine Linux `3.22.x`, `3.23.x`
* Debian `12` (`Bookworm`), `13` (`Trixie`)
* Fedora `43`, `44`
* Rocky Linux `8.x` (`8.5` – `8.9`), `9.x` (`9.0` – `9.8`)
* Ubuntu `22.04` (`Jammy Jellyfish`), `24.04` (`Noble Numbat`), `26.04`

## Requirements

- Docker engine (installed by the dependency role `kirill_zak.docker`).
- Python 3 `requests` library on the target host (`python3-requests`, or
  `py3-requests` on Alpine): required by the `community.docker` modules
  used by the role.

## Role Variables

- `dockovpn_openvpn_docker_container_name`: Name of container. Default value `dockovpn_openvpn`.
- `dockovpn_openvpn_docker_container_volume`: Name of container volume. Default value `dockovpn_openvpn_configuration`.
- `dockovpn_openvpn_docker_host_ip`: Host IP. Default value `127.0.0.1`.
- `dockovpn_openvpn_docker_configuration_port`: Port for get configuration. Default value `8080`.
- `dockovpn_openvpn_docker_log_driver`: Logger driver. Default value is `none` for disable log. List of available logger drivers: https://docs.docker.com/config/containers/logging/configure/#supported-logging-drivers
- `dockovpn_openvpn_docker_tag`: Tag found at https://hub.docker.com/r/alekslitvinenk/openvpn/tags

## Dependencies

- Docker

## Example Playbook

```yaml
    - name: Install OpenVPN
      hosts: openvpn
      become: true
      vars:
        dockovpn_openvpn_docker_host_ip: 192.168.0.1
      roles:
        - role: kirill_zak.docker
        - role: kirill_zak.dockovpn_openvpn_docker
```

## License

GPL-2.0

## Author Information

https://kirill-zak.ru