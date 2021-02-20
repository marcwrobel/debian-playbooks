## Requirements

The following instructions assume you have Python 3 and Docker installed. On Debian 10 run :

    sudo apt install pipenv

## Prepare development environment

This project needs [Ansible](https://www.ansible.com/), [YAMLlint](https://yamllint.readthedocs.io/en/stable/) and
[Ansible-lint](https://github.com/ansible/ansible-lint).

The best and easiest way to install those dependencies is to use [`pipenv`](https://pipenv.pypa.io).

    pipenv install
    pipenv shell
    ansible --version
    yamllint --version
    ansible-lint --version

## Run linting

Linting is performed at repository level using YAMLlint and Ansible-lint :

    cd <repository>
    yamllint .
    ansible-lint

## Continuous integration

The GitHub Action workflow [`CI`](https://github.com/marcwrobel/ansible-collection-assertions/actions?query=workflow%3ACI) is executed for each commit, on merge
request (targeting the `main` branch) and at least once a week on saturday morning. This workflow runs linting with YAMLlint and Ansible-lint.
