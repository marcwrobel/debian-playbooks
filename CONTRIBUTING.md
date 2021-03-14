## Requirements

The following instructions assume [`pipenv`](https://pipenv.pypa.io) is installed. On Debian 10 run :

    sudo apt install pipenv

## Prepare development environment

This project needs [Ansible](https://www.ansible.com/) and [Ansible-lint](https://github.com/ansible/ansible-lint). The best and easiest way to install those
dependencies is to use the provided scripts :

    bin/setenv

In order to get the currently installed versions :

    bin/versions

## Run linting

Linting is performed at repository level using Ansible-lint (it runs transparently YAMLlint) :

    cd <repository>
    ansible-lint

## Continuous integration

The GitHub Action workflow [`CI`](https://github.com/marcwrobel/ansible-collection-assertions/actions?query=workflow%3ACI) is executed for each commit, on merge
request (targeting the `main` branch) and at least once a week on saturday morning. This workflow runs linting with YAMLlint and Ansible-lint.
