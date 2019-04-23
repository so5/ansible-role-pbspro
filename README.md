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
pbspro_child_nodes: []
pbspro_run_job_on_server: True
pbspro_qmgr_cmds: []
pbspro_installation: True
pbspro_setup: True
```

please note ```pbspro_server_hostname``` is not set by default.
if it is not set ```PBS_SERVER``` in /etc/pbs.conf is set to localhost.
so you have to set this variable explicitly  in multi node encironment

acceptable values for ```pbspro_version``` is in vars/main.yml but this role
is tested only with v19.1.1 for now

- ```pbspro_child_nodes``` is list of child node's hostnames. this value will be used by qmgr to create vnode setting.
- ```pbspro_qmgr_cmds``` is list of qmgre commands. if this value is set, qmgr -c will be issued with each element at the end of play.
- ```pbspro_run_job_on_server``` is flag variable, if true, pbsserver node will accept jobs(MOM will be started on server node). default value is True.
- ```pbspro_prebuild``` is not supported for now. If you turn this variable True, install prebuild binaries instead of building from source.
- if ```pbspro_installation``` is True and ```pbspro_setup``` is false, this role only install PBSPro. In an opposite case, this role only setup existing PBSPro


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
