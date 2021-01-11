# ahadns 

role to setup a fully configured AhaDNS DNS server supporting plain DNS, DOH and DOT protocols

Requirements
------------

```yaml
ansible-galaxy install -r requirements.yml
```

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

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

HybridAdmin
