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

pbspro\_server\_hostname is not defined by default. you have to pass this value to the role, otherwise
child node can not communicate with pbs pro server!

please note, this role is tested only with lates version (v19.1.1 for now)

pbspro\_prebuild is not supported for now. If you turn this variable True, install prebuild binaries instead of building from source.

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
