# apache_server

Install the [Apache HTTP Server](https://httpd.apache.org/).

## Requirements

None.

## Dependencies

- [community.general.apache2_module](https://docs.ansible.com/ansible/latest/collections/community/general/apache2_module_module.html)

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

See `defaults/main.yml` for more information.

## Usage

    - hosts: desktop
      roles:
        - role: 'marcwrobel.debian_apache.apache_server'

## Links

None.
