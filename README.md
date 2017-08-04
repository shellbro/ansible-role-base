Role Name
=========

Ansible role that provides base configuration for Fedora and CentOS.

Requirements
------------

None

Role Variables
--------------

- hostname (defaults to {{ inventory_hostname }})
- shell_accounts (by default empty list)
- admin_email

Dependencies
------------

- shellbro.epel

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: shellbro.common
           shell_accounts: 
           - login: jsmith
             supplementary_groups: wheel
           admin_email: admin@example.com

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
