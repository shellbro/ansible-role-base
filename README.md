base
====

[![Build Status](https://travis-ci.org/shellbro/ansible-role-base.svg?branch=master)](https://travis-ci.org/shellbro/ansible-role-base)

Ansible role that provides base configuration for Fedora and CentOS 7.

Requirements
------------

Ansible version >= 2.3.

Role Variables
--------------

* hostname (defaults to {{ inventory_hostname }})
* timezone (defaults to UTC)
* ntp_client - force time synchronization with NTP (by default no)
* shell_accounts (by default empty list)
* root_alias (required)
* persistent_journal - force persistent journal (by default no)
* auto_update - whether OS updates should be applied automatically (by default no)
* vmware_tools - force installation of VMWare Tools (by default no)

Dependencies
------------

* shellbro.epel

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: shellbro.base
          hostname: example.com
          timezone: Europe/Warsaw
          ntp_client: yes
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
