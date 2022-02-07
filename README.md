[![Build](https://github.com/marcwrobel/debian-playbooks/workflows/CI/badge.svg)](https://github.com/marcwrobel/debian-playbooks/actions)

# Debian playbooks

A set of opinionated [Ansible](https://www.ansible.com/) playbooks, collections and roles for Debian 11.

## Requirements

Playbooks, collections and roles in this repository needs Ansible 2.12+ and are targeted for Debian 11.

For Ansible installation and own requirements have a look at [the official documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

## Getting started

Once Ansible has been installed you can clone this repository, prepare an inventory, and run the
playbooks :

    ansible-playbook -i /path/to/hosts laptops.yml --diff --check
    ansible-playbook -i /path/to/hosts servers.yml --diff --check

## Development

Take a look at the [Contributing guide](/CONTRIBUTING.md).

## Resources

- [Ansible tips & tricks](https://www.marcwrobel.fr/ansible)
- [A great collection of Docker container for Ansible playbook and role testing](https://hub.docker.com/u/geerlingguy)
- [Ansible - Testing Strategies](https://docs.ansible.com/ansible/latest/reference_appendices/test_strategies.html)
