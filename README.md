# ahadns

![CI](https://github.com/hybridadmin/ansible-role-ahadns/workflows/CI/badge.svg?branch=main)

> Role to setup a fully configured AhaDNS DNS server supporting plain DNS, DOH and DOT protocols

Requirements
------------

The command below should be run to install any dependant ansible roles: 
```yaml
ansible-galaxy install -r requirements.yml
```

Role Variables
--------------

The variables below are set in `defaults/main.yml`:
```yaml
# doh server variables
doh_version: 2.2.4

# golang variables
golang_ver: "1.15.6"
golang_path: /opt

# .NET SDK variables
dotnet_version: 5.0

# Aha.Dns.Statistics variables
stats_api_version: 1.0.1

# Letsencrypt variables
server_fqdn: "dns-server.com"
doh_endpoint: "doh.{{ server_fqdn }}"
dot_endpoint: "dot.{{ server_fqdn }}"

letsencrypt_email: "test@test.com"

# Nginx dhparam hardening variables
dhparam_key_size: 4096
```

Dependencies
------------

N/A

Example Playbook
----------------

```yaml
  hosts: all
  vars:
    dhparam_key_size: 2048
    dhparam_remote_get: true
  roles:
    - role: "hybridadmin_ahadns"
```

License
-------

GPL-3.0 License

Author Information
------------------

Hybridadmin
