# nodenv

[![Build Status](https://travis-ci.org/eendroroy/ansible-role-nodenv.svg?branch=master)](https://travis-ci.org/eendroroy/ansible-role-nodenv)


[![GitHub tag](https://img.shields.io/github/tag/eendroroy/ansible-role-nodenv.svg)](https://github.com/eendroroy/ansible-role-nodenv/tags)

[![Contributors](https://img.shields.io/github/contributors/eendroroy/ansible-role-nodenv.svg)](https://github.com/eendroroy/ansible-role-nodenv/graphs/contributors)
[![GitHub last commit (branch)](https://img.shields.io/github/last-commit/eendroroy/ansible-role-nodenv/master.svg)](https://github.com/eendroroy/ansible-role-nodenv)
[![license](https://img.shields.io/github/license/eendroroy/ansible-role-nodenv.svg)](https://github.com/eendroroy/ansible-role-nodenv/blob/master/LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/eendroroy/ansible-role-nodenv.svg)](https://github.com/eendroroy/ansible-role-nodenv/issues)
[![GitHub closed issues](https://img.shields.io/github/issues-closed/eendroroy/ansible-role-nodenv.svg)](https://github.com/eendroroy/ansible-role-nodenv/issues?q=is%3Aissue+is%3Aclosed)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/eendroroy/ansible-role-nodenv.svg)](https://github.com/eendroroy/ansible-role-nodenv/pulls)
[![GitHub closed pull requests](https://img.shields.io/github/issues-pr-closed/eendroroy/ansible-role-nodenv.svg)](https://github.com/eendroroy/ansible-role-nodenv/pulls?q=is%3Apr+is%3Aclosed)

Ansible role to install nodenv

### Role Variables

Set `nodenv_env: system` to install nodenv system-wide, or `nodenv_env: local` for local installation.

Add plugins under `nodenv.plugins` var.

Define node versions to install under `nodes` var.

Example:

```yml
nodenv_env: system

nodenv:
  plugins:
    - { name: node-build, repo: 'https://github.com/nodenv/node-build.git' }

nodes:
  - version: 9.11.1
```

### Supported OS

- Ubuntu
    - precise (12.04)
    - trusty  (14.04)
    - xenial  (16.04) - xenial requires python2 to be installed for ansible support
- CentOS
    - 6
    - 7
- RHEL
    - 6
    - 7

### Example Playbook

```yml
---
# Example playbook
- name: nodenv setup
  hosts: servers
  gather_facts: yes

  tasks:
  - include_role:
      name: eendroroy.nodenv
    vars:
      nodenv_env: system
      pythons:
        - version: 9.11.1
```

## Contributing

Bug reports and pull requests are welcome on GitHub at [ansible-role-nodenv](https://github.com/eendroroy/ansible-role-nodenv) repository.
This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Author

* **indrajit** - *Owner* - [eendroroy](https://github.com/eendroroy)

## License

The project is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).