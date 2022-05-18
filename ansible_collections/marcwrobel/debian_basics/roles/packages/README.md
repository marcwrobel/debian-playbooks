# packages

Manage basic packages commonly needed (or not) on Debian, but not always installed by default.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    packages__group_blacklist: []
    packages__host_blacklist: []
    packages__group_list: []
    packages__host_list: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      collections:
        - 'marcwrobel.debian_basics'
      roles:
        - { role: 'packages', tags: [ 'packages' ] }

## Links

- [pkgs.org](https://pkgs.org)
