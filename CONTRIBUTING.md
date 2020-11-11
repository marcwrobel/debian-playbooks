## Requirements

The following instructions assume you have Python 3 installed along with [`python3-pip`](https://pip.pypa.io/en/stable/), [`python3-venv`](https://docs.python.org/3/library/venv.html)
[`python3-wheel`](https://pythonwheels.com/) and `libssl-dev` (for Molecule) on Debian 10.

    sudo apt install python3-pip python3-venv python3-wheel libssl-dev

[Docker](https://www.docker.com/) must also be installed to run the tests. Have a look at the [official documentation](https://docs.docker.com/engine/install/debian/)
for installation instructions.

## Prepare development environment

This project needs [Ansible](https://www.ansible.com/), [YAMLlint](https://yamllint.readthedocs.io/en/stable/), [Ansible-lint](https://github.com/ansible/ansible-lint)
and [Molecule](https://molecule.readthedocs.io/en/stable/).

The best and easiest way to install those dependencies is to use the `requirements.txt` in a Python [virtual environment](https://docs.python.org/3/library/venv.html).

    python3 -m venv .environments/ansible
    source .environments/ansible/bin/activate
    pip install -r requirements.txt

    ansible --version
    yamllint --version
    ansible-lint --version
    molecule --version

## Run linting

Linting is performed at repository level using YAMLlint and Ansible-lint :

    cd <repository>
    yamllint .
    ansible-lint

## Run integration tests

Integration tests are performed at collection level using Molecule :

    cd <repository>/ansible_collections/marcwrobel/<collection>
    molecule test

During the development lifecycle you may prefer to keep the instances running and run `molecule`
commands individually:

    # Creates and configures instances
    molecule converge

    # Runs automated tests against instances
    molecule verify

    # Runs the converge step a second time and check that no tasks are marked as changed
    molecule idempotence

## Continuous integration

The GitHub Action workflow [`CI`](https://github.com/marcwrobel/debian-playbooks/actions?query=workflow%3ACI)
is executed for each commit on or merge request targeting the `main` branch (and at least once a
week on saturday morning). This workflow runs :

- linting with YAMLlint and Ansible-lint,
- integration tests on collections with Molecule.
