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
- root_alias
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
             alias: admin@example.com
           - login: bot
             supplementary_groups:
             alias: root
           root_alias: jsmith
           auto_update: yes
           vmware_tools: yes

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
