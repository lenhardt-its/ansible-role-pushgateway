# Ansible Role: Pushgateway

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![centos-7](https://img.shields.io/badge/centos-7.x-orange?style=flat&logo=centos)](https://www.centos.org/)
[![centos-8](https://img.shields.io/badge/centos-8.x-orange?style=flat&logo=centos)](https://www.centos.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-pushgateway?style=flat)](https://github.com/OnkelDom/ansible-role-pushgateway/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-pushgateway.svg?style=flat)](https://github.com/OnkelDom/ansible-role-pushgateway/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-pushgateway/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-pushgateway)

## Description

Deploy prometheus [Pushgateway](https://github.com/prometheus/pushgateway) using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)
- Community Packages: `ansible-galaxy collection install community.general`

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `pushgateway_version` | 1.2.0 | Node exporter package version |
| `pushgateway_web_listen_address` | 0.0.0.0 | default listen address |
| `pushgateway_web_listen_port` | 9091 | default listen port |
| `pushgateway_web_external_url` | "http://{{ ansible_domain }}.{{ ansible_hostname }}:{{ pushgateway_web_listen_port }}" | External address on which pushgateway is available. Useful when behind reverse proxy. Ex. http://example.org/pushgateway |
| `pushgateway_persistence` | true | Enable persistence file |
| `pushgateway_create_consul_agent_service` | "true" | Add consul agent config snipped |
| `pushgateway_config_flags_extra` | {} | Additional configuration flags passed at startup to pushgateway binary |
| `pushgateway_allow_firewall` | false | allow on firewall |
| `pushgateway_system_user` | prometheus | default system user |
| `pushgateway_system_group` | prometheus | default system group |
| `pushgateway_log_level` | warn | default log level |
| `pushgateway_log_format` | json | default log format |
| `pushgateway_binary_local_dir` | /usr/local/bin | defaulr bin dir |
| `pushgateway_persistence_dir` | /var/lib/pushgateway | default data dir |
| `pushgateway_config_flags_extra` | {} | additional startup params |

## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  roles:
    - onkeldom.pushgateway
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
