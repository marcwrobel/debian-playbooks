# firewalld

Install and configure `firewalld`.

Only [firewalld predefined zones](https://firewalld.org/documentation/zone/predefined-zones.html) can be used for the
time being.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    firewalld__sources: []
    firewalld__services: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      roles:
        - role: 'marcwrobel.debian_basics.firewalld'
          vars:
            firewalld__sources: [{ zone: 'internal', source: '192.168.0.1', permanent: true, state: 'enabled', immediate: true }]
            firewalld__services: [{ zone: 'internal', service: 'ssh', permanent: true, state: 'enabled', immediate: true }]

## Links

N/A
