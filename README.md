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
  first_entry:
    name: ...
    state: ...
    use: ...
  second_entry:
    .
    .
    .
  .
  .
  .
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
      pkg1:
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
      pkg2:
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
      pkg3:
        name: ntpdate
        state: absent
  roles:
    - turcumihaiioan.system_package
```

#### Install, remove and upgrade packages in a specific order:
```yml
- hosts: servers
  vars:
    system_package:
      pkg4:
        name: at
        state: present
      pkg5:
        name:
          - httpd
          - ntpdate
        state: absent
      pkg6:
        name: chrony
        state: latest
      pkg7:
        name: at
        state: latest
  roles:
    - turcumihaiioan.system_package
```

License
-------

GPL-3.0-only

Author Information
------------------

Role created by Turcu Mihai Ioan
