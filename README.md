# pm2

[![Build Status](https://travis-ci.org/pari-/ansible-pm2.svg?branch=master)](https://travis-ci.org/pari-/ansible-pm2)

An Ansible role which installs and configures the production process manager for Node.JS applications

<!-- toc -->

- [Requirements](#requirements)
- [Example](#example)
- [Role Variables](#role-variables)
- [Dependencies](#dependencies)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: jessie). It is assumed to work on other Debian distributions as well.

Ansible version compatibility:

- __2.3.1.0__ (current version in use for development of this role) 
- 2.2.3.0
- 2.1.6.0
- 2.0.2.0

## Example

```yaml
---

- hosts: "{{ hosts_group | default('all') }}"

  vars:

  roles:
    - { role: "ansible-nodejs", tags: ['nodejs'] }
    - { role: "{{ role_name | default('ansible-pm2') }}", tags: ['pm2'] }

```

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml). They're generally prefixed with `pm2_` (which I deliberately leave out here for better formatting).

variable | default | notes
-------- | ------- | -----
`bin` | `"/usr/bin/pm2"` | `Path to the 'pm2'-binary` 
`npm_global` | `"yes"` | `Install the node.js library globally`
`npm_name` | `"pm2"` | `The name of the 'pm2'-npm-package that is to be installed`
`npm_production` | `"yes"` | `Install dependencies in production mode, excluding devDependencies`
`startup_user` | `"root"` | `The user under which pm2's startup script is executed under`
`supported_distro_list` | `['jessie']` | `A list of distribution releases this role supports`
`version` | `"2.4.6"` | `Version of the 'pm2'-npm-package that is to be installed

## Dependencies

- [ansible-nodejs](https://github.com/pari-/ansible-nodejs)

## License

MIT

## Author Information

* Patrick Ringl
