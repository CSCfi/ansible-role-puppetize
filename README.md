[![Build Status](https://travis-ci.org/CSCfi/ansible-role-puppetize.svg?branch=master)](https://travis-ci.org/CSCfi/ansible-role-puppetize)

ansible-role-puppetize
=========

A role for bootstrapping puppet clients.

Requirements
------------

N/A

Role Variables
--------------

Dependencies
------------

Example Playbook
----------------

```
- hosts: backend_servers
  become: yes
  become_user: root
  roles:
    - ansible-role-puppetize
```

License
-------

MIT

Author Information
------------------

CSC - IT Center for Science
