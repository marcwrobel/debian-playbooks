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

### Run linting

Linting is performed at repository level using [YAMLlint](https://yamllint.readthedocs.io/en/stable/)
and [Ansible-lint](https://github.com/ansible/ansible-lint) :

    yamllint .
    ansible-lint

### Run integration tests

Integration tests are performed at collection level using [Molecule](https://molecule.readthedocs.io/en/stable/) :

    cd ansible_collections/marcwrobel/<collection>
    molecule test

During the development lifecycle you may prefer to keep the instances running and run `molecule`
commands individually:

    # Use the provisioner to create and configure instances
    molecule converge

    # Run automated tests against instances
    molecule verify

### Continuous integration

The GitHub Action workflow [`CI`](https://github.com/marcwrobel/debian-playbooks/actions?query=workflow%3ACI)
is executed for each commit on or merge request targeting the `main` branch (and at least once a
week on saturday morning). This workflow runs :

- linting ([YAMLlint](https://yamllint.readthedocs.io/en/stable/), [Ansible-lint](https://github.com/ansible/ansible-lint)),
- [Molecule](https://molecule.readthedocs.io/en/stable/) tests on collections.

## Links

- [Ansible tips & tricks](https://www.marcwrobel.fr/ansible)
- [A great collection of Docker container for Ansible playbook and role testing](https://hub.docker.com/u/geerlingguy)
- [Ansible - Testing Strategies](https://docs.ansible.com/ansible/latest/reference_appendices/test_strategies.html)
- [How to add integration tests to an Ansible collection with Molecule](https://www.jeffgeerling.com/blog/2019/how-add-integration-tests-ansible-collection-molecule)
