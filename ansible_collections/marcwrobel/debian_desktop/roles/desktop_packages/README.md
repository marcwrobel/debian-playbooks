# packages

Manage basic packages commonly needed (or not) on Debian Desktop, but not always installed by default.

See `defaults/main.yml` for the full list of packages.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    desktop_packages__group_blacklist: []
    desktop_packages__host_blacklist: []
    desktop_packages__group_list: []
    desktop_packages__host_list: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      roles:
        - role: 'marcwrobel.debian_basics.packages'

## Links

- [pkgs.org](https://pkgs.org)
