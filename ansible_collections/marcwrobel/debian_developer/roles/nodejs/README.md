# nodejs

Configure [Node.js LTS](https://nodejs.org/).

Node.js is an open-source, cross-platform, back-end JavaScript runtime environment.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    nodejs__state: present
    nodejs__version: '16'

See `defaults/main.yml` for more information.

## Usage

    - hosts: laptops
      roles:
        - role: 'marcwrobel.debian_developer.nodejs'

## Links

- [NodeSource Node.js Binary Distributions](https://github.com/nodesource/distributions/blob/master/README.md)
