# virtualbox

Configure [VirtualBox](https://www.virtualbox.org).

VirtualBox is an hypervisor for x86 virtualization.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    virtualbox__state: present
    virtualbox__version: '6.1'

See `defaults/main.yml` for more information.

## Usage

    - hosts: laptops
      collections:
        - 'marcwrobel.debian_desktop'
      roles:
        - role: 'virtualbox'
          tags: [ 'virtualbox' ]

## Links

- [Download VirtualBox for Linux Hosts](https://www.virtualbox.org/wiki/Linux_Downloads)
