# kimsufi_network

Configure IPv4 / IPv6 network interfaces on a Kimsufi servers.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    kimsufi_network__interface: <none>
    kimsufi_network__ipv4_address: <none>
    kimsufi_network__ipv4_netmask: 255.255.255.0
    kimsufi_network__ipv4_gateway: <none>
    kimsufi_network__ipv6_address: <none>
    kimsufi_network__ipv6_netmask: 128
    kimsufi_network__ipv6_gateway: <none>

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      collections:
        - 'marcwrobel.debian_kimsufi'
      roles:
        - role: 'kimsufi_network'
          vars:
            kimsufi_network__interface: 'eno0'
            kimsufi_network__ipv4_address: '1.1.1.31'
            kimsufi_network__ipv4_gateway: '1.1.1.254'
            kimsufi_network__ipv6_address: '2021:40d0:a:aa1f::1'
            kimsufi_network__ipv6_gateway: '2021:40d0:a:aaff:ff:ff:ff:ff'
          tags: [ 'net' ]

## Links

- [Mettre en place l'IPv6 sur un Kimsufi](https://mondedie.fr/d/11360-mettre-en-place-lipv6-sur-un-kimsufi/3)
