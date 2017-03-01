# pm2

An Ansible role which installs and configures the production process manager for Node.JS applications

<!-- toc -->

- [Requirements](#requirements)
- [Example](#example)
- [Role Variables](#role-variables)
  * [Role Internals](#role-internals)
- [Dependencies](#dependencies)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: jessie). It is assumed to work on other Debian distributions as well.

Ansible version in use for development: 2.2.1

## Example

```yaml
- hosts: pm2-servers

  roles: 
    - { role: ansible-pm2 }
```

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

### Role Internals

variable | default | notes
-------- | ------- | -----
`pm2_supported_distro_list` | `['jessie']` | `A list of distribution releases this role supports`
`pm2_npm_name` | `"pm2"` | `The name of the 'pm2'-npm-package that us to be installed`
`pm2_npm_production` | `"yes"` | `Install dependencies in production mode, excluding devDependencies`
`pm2_npm_state` | `"present"` | `The state of the node.js library`
`pm2_npm_global` | `"yes"` | `Install the node.js library globally`
`pm2_bin` | `"/usr/bin/pm2"` | `Path to the 'pm2'-binary` 

## Dependencies

- [ansible-nodejs](https://github.com/pari-/ansible-nodejs)

## License

MIT

## Author Information

* Patrick Ringl
