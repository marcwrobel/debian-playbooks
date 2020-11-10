# banner

An often forgotten area in system protection is a well-formed banner text. This role configures
`/etc/motd` in order to display such banner after a user has logged in, and immediately before the
shell is started.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    banner__message: >-
      Unauthorized access to this device is prohibited. You must have explicit, authorized permission to
      access or configure this device. Unauthorized attempts and actions to access or use this system
      may result in civil and/or criminal penalties. All activities performed on this device are logged
      and monitored.

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      roles:
         - { role: marcwrobel.debian_basics.banner }

## Links

- [Banner Files](https://wiki.centos.org/TipsAndTricks/BannerFiles)
