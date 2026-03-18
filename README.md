OpenVPN-Server Setup
=========

A role for automated deployment of a OpenVPN server on Linux. The role will allow you to create a local network through a tunnel. The role supports deployment on ubuntu 22.04.

Requirements
------------

- Ansible ≥ 2.1
- Access to the server with sudo rights
- Static IP address on server

Role Variables
--------------

| Variable | Default | Description |
|----------|---------|-------------|
| `openvpn_dir` | `/etc/openvpn` | The directory with OpenVPN config files |
| `openvpn_easyrsa_dir` | `/usr/share/easy-rsa` | The directory with easy-rsa keys |
| `openvpn_clients` | `[client_rick,client_morty]` | List of openvpn clients |
| `openvpn_port` | `1194` | OpenVPN external port |
| `openvpn_protocol` | `udp` | Protocol of tunnel |
| `openvpn_subnet` | `10.9.0.0` | The subnet of OpenVpn network |
| `openvpn_subnet_mask` | `255.255.255.0` | The subnet mask of OpenVpn network |
| `openvpn_external_address` | `{{ ansible_default_ipv4.address }}` | IP address of OpenVPN server |
| `openvpn_external_interface` | `eth0` | External network interface of OpenVPN server |

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```yml
- hosts: vpn
  become: yes
  roles:
   - ansible-role-openvpn
```

License
-------

MIT License

