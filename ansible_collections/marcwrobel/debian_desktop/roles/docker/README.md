# docker

Install and configure [Docker](https://vscodium.com/).

Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    docker__state: present

See `defaults/main.yml` for more information.

## Usage

    - hosts: laptops
      roles:
        - role: 'marcwrobel.debian_desktop.docker'

## Links

- [Install Docker Engine on Debian](https://docs.docker.com/engine/install/debian/#install-using-the-repository)
