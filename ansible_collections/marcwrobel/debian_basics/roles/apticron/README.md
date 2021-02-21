# Apticron

Configure Apticron to get daily email alerts for pending package updates.

This role use [`apticron-systemd`](https://packages.debian.org/buster/apticron-systemd), which trigger Apticron using systemd timers.

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
        - role: 'apticron'

## Links

- [apticron(1)](https://manpages.debian.org/buster/apticron/apticron.1.en.html)
