[![Build Status](https://travis-ci.org/CSCfi/ansible-role-puppetize.svg?branch=master)](https://travis-ci.org/CSCfi/ansible-role-puppetize)

ansible-role-puppetize
=========

A role for bootstrapping puppet clients.

Requirements
------------

N/A

Role Variables
--------------

See defaults/main.yml for current defaults, but as some information:

puppet_run_only: Boolean (true or false). Default false. Only run Puppet without installing it.
puppetize_time_difference: Integer. Default 120. Maximum difference of time to accept the certificate.
puppetize_manage_yumrepo: Boolean (true or false). Default false. Ensure the YUM repository is configured.
puppetize_enable_puppet: Boolean (true or false). Default false. Enable puppet agent.
noop_run: Boolean (true or false). Default false. Run puppet agent with --noop option that should not apply changes.

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

Testing
-------

This bit is manual, we do some testing in this role already but it does not setup a puppetmaster+agent.

Basic environment needed: an agent and a puppetmaster on different VMs/tainers with different FQDNs.

When testing this role it's a good idea to run it on a node:
  - which is already puppetized from before
  - which is not puppetized before (generate CSR and sign the certificate)
  - where we only run some tasks with -e '{\"puppet_run_only\":true}' (remove backslashes before running)

Author Information
------------------

CSC - IT Center for Science
