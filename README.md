system_package
=========

This role allows you to use the ansible.builtin.package module to manage packages.

Requirements
------------

ansible >= 2.10

Role Variables
--------------

```yml
system_package:
  name: ...
  state: ...
  use: ...
```

Dependencies
------------

None

Example Playbook
----------------

#### Install a package:
```yml
- hosts: servers
  vars:
    system_package:
      name: ntpdate
      state: present
  roles:
    - turcumihaiioan.system_package
```

#### Install a package with the latest available version:
```yml
- hosts: servers
  vars:
    system_package:
      name: ntpdate
      state: latest
  roles:
    - turcumihaiioan.system_package
```

#### Remove a package:
```yml
- hosts: servers
  vars:
    system_package:
      name: ntpdate
      state: absent
  roles:
    - turcumihaiioan.system_package
```

License
-------

GPL-3.0-only

Author Information
------------------

Role created by Turcu Mihai Ioan
