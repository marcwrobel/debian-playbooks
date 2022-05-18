# firewalld

Install and configure `firewalld`.

## Requirements

None.

## Dependencies

None.

## Role Variables

None.

## Usage

    - hosts: servers
      collections:
        - 'marcwrobel.debian_basics'
      roles:
        - { role: 'firewalld', tags: [ 'fw' ] }

## Links

- [Banner Files](https://www.tecmint.com/sudoers-configurations-for-setting-sudo-in-linux/)
