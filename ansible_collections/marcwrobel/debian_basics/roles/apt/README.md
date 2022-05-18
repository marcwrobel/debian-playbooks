# APT

APT configuration :
- basic configuration,
- repositories configuration,
- auto-upgrade with `UnattendedUpgrades`,
- changelogs with `apt-listchanges`.

Backports are always enabled : only manually installed older packages are upgraded to newer ones from backports.

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
        - role: 'apt'

## Links

- [UnattendedUpgrades](https://wiki.debian.org/UnattendedUpgrades)
