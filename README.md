# pm2

[![Build Status](https://travis-ci.org/pari-/ansible-pm2.svg?branch=master)](https://travis-ci.org/pari-/ansible-pm2)

An Ansible role which installs and configures the production process manager for Node.JS applications

<!-- toc -->

- [Requirements](#requirements)
- [Example](#example)
- [Variables](#variables)
  * [Role Variables](#role-variables)
  * [Role Internals](#role-internals)
- [Dependencies](#dependencies)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: jessie). It is assumed to work on other Debian distributions as well.

Ansible version compatibility:

- __2.3.0__ (current version in use for development of this role)
- 2.2.2
- 2.1.5
- 2.0.2

## Example

```yaml
- hosts: pm2-servers

  vars:
    nodejs_version: "node_7.x"
    nodejs_apt_key_id: "68576280"
    pm2_version: "2.4.2"

  roles: 
    - "ansible-pm2"
```

## Variables

Available variables are listed below, along with default values (see defaults/main.yml):

### Role Variables

variable | default | notes
-------- | ------- | -----
`pm2_version` | `"2.4.2"` | `Version of the 'pm2'-npm-package that is to be installed

### Role Internals

variable | default | notes
-------- | ------- | -----
`pm2_bin` | `"/usr/bin/pm2"` | `Path to the 'pm2'-binary` 
`pm2_npm_global` | `"yes"` | `Install the node.js library globally`
`pm2_npm_name` | `"pm2"` | `The name of the 'pm2'-npm-package that is to be installed`
`pm2_npm_production` | `"yes"` | `Install dependencies in production mode, excluding devDependencies`
`pm2_npm_state` | `"present"` | `The state of the node.js library`
`pm2_supported_distro_list` | `['jessie', 'trusty']` | `A list of distribution releases this role supports`

## Dependencies

- [ansible-nodejs](https://github.com/pari-/ansible-nodejs)

## License

MIT

## Author Information

* Patrick Ringl
