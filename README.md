Role Name
=========

build, install and setup pbspro ( https://www.pbspro.org )


Requirements
------------

git module is used to get source tar ball.
any other prerequesties will be installed by this role

Role Variables
--------------

```
pbspro_prefix: "/opt/pbs"
pbspro_version: "v19.1.1"
pbspro_prebuild: False
pbspro_server: True
```

Dependencies
------------

None.

Example Playbook
----------------

```
    - hosts: batchServer
      roles:
         - { role: so5.pbspro}
    - hosts: jobServer
      roles:
         - { role: so5.pbspro, pbspro_server: False}
```

License
-------

MIT

Author Information
------------------

This role is created by Naoyuki Sogo.
