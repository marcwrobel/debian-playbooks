# apache_server

Install the [Apache HTTP Server](https://httpd.apache.org/).

Only the event Multi-Processing Module (MPM) can be used with this role.

The `*_available` / `*_enable` configuration scheme, traditionally used on Debian, has not been
adopted by this role to avoid as much as possible Ansible-unmanaged configurations (and also because
`community.general.apache2_*` modules are really slow). Those directories are deleted by this role
to avoid misinterpretations.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    # Whether Apache must be installed (`present`) or not (`absent`).
    apache_server__state: 'absent'
    apache_server__bindings:
    - name: 'localhost'
      ip: '127.0.0.1'
      ports: [80]
    apache_server__ulimit_max_files: 65536
    apache_server__arguments: ''
    apache_server__mpm_event_start_servers: 2
    apache_server__mpm_event_min_spare_threads: 25
    apache_server__mpm_event_max_spare_threads: 75
    apache_server__mpm_event_thread_limit: 64
    apache_server__mpm_event_threads_per_child: 25
    apache_server__mpm_event_max_request_workers: 150
    apache_server__mpm_event_max_connections_per_child: 0

See `defaults/main.yml` for more information.

## Usage

    - hosts: desktop
      roles:
        - role: 'marcwrobel.debian_apache.apache_server'

## Links

None.
