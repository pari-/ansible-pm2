# pm2

[![Build Status](https://travis-ci.org/pari-/ansible-pm2.svg?branch=master)](https://travis-ci.org/pari-/ansible-pm2)

An Ansible role which installs and configures the production process manager for Node.JS applications

<!-- toc -->

- [Requirements](#requirements)
- [Example](#example)
- [Defaults](#defaults)
- [Dependencies](#dependencies)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: stretch). It is assumed to work on other Debian distributions as well.

Ansible version compatibility: [Dockerfile](https://github.com/pari-/docker-debian-ansible/blob/master/debian/stretch/Dockerfile)

## Example

```yaml
---

- hosts: "all"
  roles:
    - role: "ansible-nodejs"
      tags:
        - "nodejs"
    - role: "ansible-pm2"
      tags:
        - "pm2"
  post_tasks:
    - block:
        - include: "tests/test_installed_pm2_version.yml"
      tags:
        - "tests"
```

## Defaults

Available variables are listed below, along with default values (see defaults/main.yml). They're generally prefixed with `pm2_` (which I deliberately leave out here for better formatting).

variable | default | notes
-------- | ------- | -----
`bin` | `/usr/bin/pm2` | `Path to the 'pm2'-binary` 
`npm_global` | `yes` | `Install the node.js library globally`
`npm_name` | `pm2` | `The name of the 'pm2'-npm-package that is to be installed`
`npm_production` | `yes` | `Install dependencies in production mode, excluding devDependencies`
`startup_user` | `root` | `The user under which pm2's startup script is executed under`
`supported_distro_list` | `['stretch']` | `A list of distribution releases this role supports`
`version` | `2.10.4` | `Version of the 'pm2'-npm-package that is to be installed`

## Dependencies

- [ansible-nodejs](https://github.com/pari-/ansible-nodejs)

## License

MIT

## Author Information

* Patrick Ringl
