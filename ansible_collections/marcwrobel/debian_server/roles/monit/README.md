# monit

Install [Monit](https://mmonit.com/monit/).

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    monit__state: 'absent'

See `defaults/main.yml` for more information.

## Usage

    - hosts: server
      roles:
        - role: 'marcwrobel.debian_server.monit'
          vars:
            monit__state: 'present'

## Links

- https://mmonit.com/monit/documentation/monit.html
