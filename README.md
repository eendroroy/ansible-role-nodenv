nodenv
======

[![Build Status](https://travis-ci.org/eendroroy/ansible-role-nodenv.svg?branch=master)](https://travis-ci.org/eendroroy/ansible-role-nodenv)

Ansible role to install nodenv

Role Variables
--------------

Set `env: system` to install nodenv system-wide, or `env: local` for local installation.

Add plugins under `plugins` var.

Define python versions to install under `pythons` var.

Example:

```yml
env: system
plugins:
  - { name: node-build, repo: 'https://github.com/nodenv/node-build.git' }

nodes:
  - version: 7.10.0
```

Supported OS
------------

- Ubuntu
    - precise (12.04)
    - saucy (13.10)
    - trusty (14.04)
    - xenial (16.04) - xenial requires python2 to be installed for ansible support

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: eendroroy.nodenv }

License
-------

MIT

Author Information
------------------

**Indrajit Roy** - *owner* - [eendroroy](https://github.com/eendroroy)