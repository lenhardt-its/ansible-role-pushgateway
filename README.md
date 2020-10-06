# Ansible Role: pushgateway

## Description

Deploy prometheus [pushgateway](https://github.com/prometheus/pushgateway) using ansible.

## Requirements

- Ansible >= 2.6 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `pushgateway_version` | 1.0.0 | Node exporter package version |
| `pushgateway_web_listen_address` | "0.0.0.0:9091" | Address on which node exporter will listen |
| `pushgateway_web_external_url` | "" | External address on which pushgateway is available. Useful when behind reverse proxy. Ex. http://example.org/pushgateway |
| `pushgateway_persistence` | true | Enable persistence file |
| `pushgateway_create_consul_agent_service` | "true" | Add consul agent config snipped |
| `pushgateway_config_flags_extra` | {} | Additional configuration flags passed at startup to pushgateway binary |

## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  roles:
    - ansible-role-pushgateway
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
