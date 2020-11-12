# bootstrap

Bootstrap a freshly installed Debian system for Ansible management.

This module:

- upgrade packages and reboot (if something was upgraded),
- install `python-apt` (required for check mode by the [APT module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html#requirements))

## Requirements

This role assumes :
- a host file has been configured in Ansible inventory file,
- managed nodes have an OpenSSH server installed,
- at least one user have an administrator SSH access to the managed nodes.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    bootstrap__upgrade_packages: true
    bootstrap__reboot_after_upgrade: true
    bootstrap__reboot_timeout: 600
    bootstrap__python_apt_package: 'python3-apt'

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      collections:
        - 'marcwrobel.debian_basics'
      roles:
        - { role: 'bootstrap', tags: [ 'bootstrap' ] }
