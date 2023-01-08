# apache_server

Install the [Apache HTTP Server](https://httpd.apache.org/).

## Requirements

None.

## Dependencies

- [community.general.apache2_module](https://docs.ansible.com/ansible/latest/collections/community/general/apache2_module_module.html)

## Role Variables

Available variables are listed below, along with default values:

    apache_server__state: 'absent'

See `defaults/main.yml` for more information.

## Usage

    - hosts: desktop
      roles:
        - role: 'marcwrobel.debian_apache.apache_server'

## Links

None.
