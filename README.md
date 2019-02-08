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
pbspro_version: latest
pbspro_use_pre_build: no
```

Dependencies
------------

None.

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
```

License
-------

MIT

Author Information
------------------

This role is created by Naoyuki Sogo.
