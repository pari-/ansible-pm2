# ansible-pm2

An Ansible role which installs and configures the production process manager for Node.JS applications

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: jessie). It is assumed to work on other Debian distributions as well.

Ansible version in use for development: 2.2.0

## Example

```yaml
- hosts: pm2-servers

  roles: 
    - { role: ansible-nodejs, nodejs_install_version: "node_7.x", nodejs_install_apt_key_id: "68576280" }
    - { role: ansible-pm2 }
```

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

### Role Internals
- `pm2_prerequisites_supported_distribution_releases`

  > A list of distribution releases this role supports.
  >
  > `['wheezy', 'jessie', 'precise', 'trusty', 'utopic', 'vivid', 'wily', 'xenial', 'yakkety']`

- `pm2_install_npm_name`

  > The name of the 'pm2'-npm-package that us to be installed
  >
  > `"pm2"`

- `pm2_install_npm_production`

  > Install dependencies in production mode, excluding devDependencies
  >
  > `"yes" `

- `pm2_install_npm_state`

  > The state of the node.js library 
  >
  > `"present"`

- `pm2_install_npm_global`

  > Install the node.js library globally 
  >
  > `"yes"`

- `pm2_configure_bin`

  > The path of the 'pm2'-binary
  >
  > `"/usr/bin/pm2"`

## Dependencies

- ansible-nodejs

## License

MIT

## Author Information

* Patrick Ringl
