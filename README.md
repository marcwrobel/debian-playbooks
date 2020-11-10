[![Build](https://github.com/marcwrobel/debian-playbooks/workflows/CI/badge.svg)](https://github.com/marcwrobel/debian-playbooks/actions)

# debian-playbooks

A set of ansible playbooks, collections and roles for Debian 10.

## Getting started

These playbooks are compatible with Ansible 2.9+. Have a look at [the official documentation to
install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).
De not forget to take a look at [control nodes](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#control-node-requirements)
and [managed nodes](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#managed-node-requirements)
requirements.

Once Ansible has been installed you can clone this repository, prepare an inventory, and run the
playbooks :

    ansible-playbook -i /path/to/hosts laptops.yml --diff --check
    ansible-playbook -i /path/to/hosts servers.yml --diff --check

## Development

### Prerequisites
The following instruction assume you are have Python 3 installed along with [`python3-pip`](https://pip.pypa.io/en/stable/)
[`python3-venv`](https://docs.python.org/3/library/venv.html) and `libssl-dev` (for Molecule) on
Debian 10.

First create a Python [virtual environment](https://docs.python.org/3/library/venv.html) :

    python3 -m venv .environments/ansible
    source .environments/ansible/bin/activate

Then install ansible and the required dependencies :

    pip install -r requirements.txt
    ansible --version

### Executing ansible-lint

Just execute the following command at the root of the project :

    ansible-lint

## Links

- [Ansible tips & tricks](https://www.marcwrobel.fr/ansible)
- [A great collection of Docker container for Ansible playbook and role testing](https://hub.docker.com/u/geerlingguy)
- [Ansible - Testing Strategies](https://docs.ansible.com/ansible/latest/reference_appendices/test_strategies.html)
- [How to add integration tests to an Ansible collection with Molecule](https://www.jeffgeerling.com/blog/2019/how-add-integration-tests-ansible-collection-molecule)
