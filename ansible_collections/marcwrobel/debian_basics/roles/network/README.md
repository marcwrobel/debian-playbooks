# network

Configure IPv4 / IPv6 network interfaces on a servers.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    network__interface: <none>
    network__ipv4_address: <none>
    network__ipv4_netmask: 255.255.255.0
    network__ipv4_gateway: <none>
    network__ipv6_address: <none>
    network__ipv6_netmask: 128
    network__ipv6_gateway: <none>

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      collections:
        - 'marcwrobel.debian_basics'
      roles:
        - role: 'network'
          vars:
            network__interface: 'eno0'
            network__ipv4_address: '1.1.1.31'
            network__ipv4_gateway: '1.1.1.254'
            network__ipv6_address: '2021:40d0:a:aa1f::1'
            network__ipv6_gateway: '2021:40d0:a:aaff:ff:ff:ff:ff'
          tags: [ 'net' ]

## Links

None.
