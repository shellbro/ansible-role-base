shellbro.base
=============

[![Build Status](https://travis-ci.org/shellbro/ansible-role-base.svg?branch=master)](https://travis-ci.org/shellbro/ansible-role-base)

Ansible role for baseline configuration of CentOS 7

Requirements
------------

Ansible version >= 2.7

Role Variables
--------------

* hostname (defaults to `inventory_hostname`)
* timezone (defaults to UTC)
* persistent_journal - configure persistent journal (by default `true`)
* root_email_alias - if provided, email address to forward root messages to
* ntp_client - configure NTP time synchronization (by default `true`)
* notify_updates - if set to `true`, email notifications are sent to root when
package updates become available (by default `true`)

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: shellbro.base
          hostname: example.com
          timezone: Europe/Warsaw
          root_email_alias: email@example.com

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
