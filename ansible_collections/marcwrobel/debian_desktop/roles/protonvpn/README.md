# protonvpn

Configure [Proton VPN](https://protonvpn.com).

Proton VPN is an high-speed Swiss VPN that safeguards your privacy.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    protonvpn__state: present

See `defaults/main.yml` for more information.

## Usage

    - hosts: laptops
      roles:
        - role: 'marcwrobel.debian_desktop.protonvpn'

## Links

- [How to install Proton VPN on Debian](https://protonvpn.com/support/official-linux-vpn-debian/)
