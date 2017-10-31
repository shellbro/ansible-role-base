base
====

[![Build Status](https://travis-ci.org/shellbro/ansible-role-base.svg?branch=master)](https://travis-ci.org/shellbro/ansible-role-base)

Ansible role that provides base configuration for Fedora and CentOS 7.

Requirements
------------

Ansible version >= 2.0.

Role Variables
--------------

- hostname (defaults to {{ inventory_hostname }})
- shell_accounts (by default empty list)
- root_alias
- persistent_journal (by default no)
- auto_update (by default no)
- vmware_tools (by default no)

Dependencies
------------

- shellbro.epel

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: shellbro.base
           hostname: example.com
           shell_accounts:
           - login: jsmith
             supplementary_groups: wheel
             alias: admin@example.com
           - login: bot
             supplementary_groups:
             alias: root
           root_alias: jsmith
           persistent_journal: yes
           auto_update: yes
           vmware_tools: yes

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
