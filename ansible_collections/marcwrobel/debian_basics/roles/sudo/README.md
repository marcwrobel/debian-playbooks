# sudo

Harden `sudo` configuration.

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
        - { role: 'sudo', tags: [ 'sudo' ] }

## Links

None.
