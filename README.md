Role Name
=========

build, install and setup pbspro ( https://www.pbspro.org )


Requirements
------------

None. prerequesties for PBS will be installed by this role

Role Variables
--------------

```
pbspro_prefix: "/opt/pbs"
pbspro_version: "v19.1.1"
pbspro_prebuild: False
pbspro_server: True
pbspro_server_hostname: "192.168.0.1"
```

please note ```pbspro_server_hostname``` is not set by default. 
if it is not set ```PBS_SERVER``` in /etc/pbs.conf is set to localhost. 
so you have to set this variable explicitly  in multi node encironment

acceptable values for ```pbspro_version``` is in vars/main.yml but this role 
is tested only with lates version (v19.1.1 for now)

```pbspro_prebuild``` is not supported for now. If you turn this variable True, install prebuild binaries instead of building from source.

Dependencies
------------

None.

Example Playbook
----------------

```
    - hosts: batchServer
      roles:
         - { "role": "so5.pbspro", "pbspro_server_hostname": "192.168.0.1" }
    - hosts: jobServer
      roles:
         - { "role": "so5.pbspro", "pbspro_server": False, "pbspro_server_hostname": "192.168.0.1" }
```

License
-------

MIT

Author Information
------------------

This role is created by Naoyuki Sogo.
