# vscodium

Configure [VSCodium](https://vscodium.com/).

VSCodium is a community-driven, freely-licensed binary distribution of Microsoft’s editor VS Code.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    vscodium__state: present

See `defaults/main.yml` for more information.

## Usage

    - hosts: laptops
      roles:
        - role: 'marcwrobel.debian_desktop.vscodium'

## Links

- [VSCodium](https://vscodium.com/#install)
