common
=========

Ansible role that provides base configuration for Fedora and CentOS.

Requirements
------------

Ansible version >= 2.0.

Role Variables
--------------

- hostname (defaults to {{ inventory_hostname }})
- shell_accounts (by default empty list)
- admin_email
- auto_update (by default no)
- vmware_tools (by default no)

Dependencies
------------

- shellbro.epel

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: shellbro.common
           hostname: example.com
           shell_accounts:
           - login: jsmith
             supplementary_groups: wheel
           admin_email: admin@example.com
           auto_update: yes

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
