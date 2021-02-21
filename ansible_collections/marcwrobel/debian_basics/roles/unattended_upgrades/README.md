# APT

Configure unattended-upgrades for automatic daily security upgrades.

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
        - role: 'unattended-upgrades'

## Links

- [How is unattended-upgrades started and how can I modify its schedule?](https://unix.stackexchange.com/a/541431)
