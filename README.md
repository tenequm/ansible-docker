# Ansible Role: Docker

This role applies Docker with daemon configurations and  docker-compose installation (it can also deletes previous version if it is installed) for Debian Jessie/Stretch and Ubuntu Xenial. It also adds Logrotate configurations for containers and volumes.

## Requirements

This role requires Ansible 2.4 or higher. Requirements are listed in the metadata file.

## Role Variables

| Variable | Required | Default | Comments |
|----------|----------|---------|----------|
| `docker_compose_install` | No | `true` | Whether to install docker-compose or not. |
| `docker_compose_path` | No | `/usr/local/bin/docker-compose` | Docker-compose bin file path. |
| `docker_compose_version` | No | `1.20.1` | Docker-compose version. |
| `docker_execute_restart` | No | `true` | Whether to execute restart after all tasks are completed. |
| `docker_enable_logrotate` | No | `true` | Whether to add logrotate configuration for container logs. |
| `docker_enable_volumes_logrotate` | No | `true` | Whether to add logrotate configuration for docker volumes logs. |

### Options for docker daemon configurations

| Variable | Required | Default | Comments |
|----------|----------|---------|----------|
| `docker_storage_driver` | No | `Undefined` | Storage driver to use |
| `docker_block_device` | No | `Undefined` | The device name used for the storage driver. |
| `docker_mount_opts` | No | `Undefined` | The mount options when mounting filesystems |
| `docker_storage_opts` | No | `Undefined` | Storage driver options |
| `docker_api_cors_header` | No | `Undefined` | Set CORS headers in the remote API |
| `docker_authorization_plugins` | No | `Undefined` | Authorization plugins to load |
| `docker_bip` | No | `Undefined` | Specify network bridge IP |
| `docker_bridge` | No | `Undefined` | Attach containers to a network bridge |
| `docker_cgroup_parent` | No | `Undefined` | Set parent cgroup for all containers |
| `docker_cluster_store` | No | `Undefined` | Set cluster store options |
| `docker_cluster_store_opts` | No | `Undefined` | Please see dockerd manual for info |
| `docker_cluster_advertise` | No | `Undefined` | Address or interface name to advertise |
| `docker_debug` | No | `Undefined` | Enable debug mode |
| `docker_default_gateway` | No | `Undefined` | Container default gateway IPv4 address |
| `docker_default_gateway_v6` | No | `Undefined` | Container default gateway IPv6 address |
| `docker_default_runtime` | No | `Undefined` | Default OCI runtime for containers |
| `docker_default_ulimits` | No | `Undefined` | Default ulimits for containers |
| `docker_disable_legacy_registry` | No | `Undefined` | Disable contacting legacy registries |
| `docker_dns` | No | `Undefined` | DNS server to us (should be a list!) |
| `docker_dns_opts` | No | `Undefined` | DNS options to use |
| `docker_dns_search` | No | `Undefined` | DNS search domains to use |
| `docker_exec_opts` | No | `Undefined` | Runtime execution options |
| `docker_exec_root` | No | `Undefined` | Root directory for execution state files |
| `docker_fixed_cidr` | No | `Undefined` | IPv4 subnet for fixed IPs |
| `docker_fixed_cidr_v6` | No | `Undefined` | IPv6 subnet for fixed IPs |
| `docker_graph` | No | `Undefined` | Root of the Docker runtime |
| `docker_group` | No | `Undefined` | Group for the unix socket |
| `docker_hosts` | No | `Undefined` | Daemon socket(s) to connect to |
| `docker_icc` | No | `Undefined` | Enable inter-container communication |
| `docker_insecure_registries` | No | `Undefined` | Enable insecure registry communication |
| `docker_ip` | No | `Undefined` | Default IP when binding container ports |
| `docker_iptables` | No | `Undefined` | Enable addition of iptables rules |
| `docker_ipv6` | No | `Undefined` | Enable IPv6 networking |
| `docker_ip_forward` | No | `Undefined` | Enable net.ipv4.ip_forward |
| `docker_ip_masq` | No | `Undefined` | Enable IP masquerading |
| `docker_labels` | No | `Undefined` | 	Set key=value labels to the daemon |
| `docker_live_restore` | No | `Undefined` | Enables keeping containers alive during daemon downtime |
| `docker_log_driver` | No | `Undefined` | Default driver for container logs |
| `docker_log_level` | No | `Undefined` | Set the logging level |
| `docker_log_opts` | No | `Undefined` | Default log driver options for containers |
| `docker_max_concurrent_downloads` | No | `Undefined` | Set the max concurrent downloads for each pull |
| `docker_max_concurrent_uploads` | No | `Undefined` | Set the max concurrent uploads for each push |
| `docker_mtu` | No | `Undefined` | Set the containers network MTU |
| `docker_oom_score_adjust` | No | `Undefined` | Set the oom_score_adj for the daemon |
| `docker_pidfile` | No | `Undefined` | Path to use for daemon PID file |
| `docker_raw_logs` | No | `Undefined` | Full timestamps without ANSI coloring |
| `docker_registry_mirrors` | No | `Undefined` | Preferred Docker registry mirror |
| `docker_runtimes` | No | `Undefined` | Register an additional OCI compatible runtime |
| `docker_selinux_enabled` | No | `Undefined` | Enable selinux support |
| `docker_swarm_default_advertise_addr` | No | `Undefined` | Set default address or interface for swarm advertised address |
| `docker_tls` | No | `Undefined` | Use TLS; implied by –tlsverify |
| `docker_tlscacert` | No | `Undefined` | Trust certs signed only by this CA |
| `docker_tlscert` | No | `Undefined` | Path to TLS certificate file |
| `docker_tlskey` | No | `Undefined` | Path to TLS key file |
| `docker_tlsverify` | No | `Undefined` | Use TLS and verify the remote |
| `docker_userland_proxy` | No | `Undefined` | Use userland proxy for loopback traffic |
| `docker_userns_remap` | No | `Undefined` | User/Group setting for user namespaces |
| `docker_http_proxy` | No | `Undefined` | Set the Docker service to use HTTP_PROXY |
| `docker_https_proxy` | No | `Undefined` | Set the Docker service to use HTTPS_PROXY |
| `docker_no_proxy_params` | No | `Undefined` | Do not proxy for Docker service params |

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
