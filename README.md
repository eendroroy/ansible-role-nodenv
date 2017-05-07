nodenv
======

[![Build Status](https://travis-ci.org/eendroroy/ansible-role-nodenv.svg?branch=master)](https://travis-ci.org/eendroroy/ansible-role-nodenv)

Ansible role to install nodenv

Role Variables
--------------

Set `nodenv_env: system` to install nodenv system-wide, or `nodenv_env: local` for local installation.

Add plugins under `nodenv.plugins` var.

Define python versions to install under `pythons` var.

Example:

```yml
nodenv_env: system

nodenv:
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

    - hosts: servers
      roles:
         - { role: eendroroy.nodenv, nodenv_env: system }

License
-------

MIT

Author Information
------------------

**Indrajit Roy** - *owner* - [eendroroy](https://github.com/eendroroy)