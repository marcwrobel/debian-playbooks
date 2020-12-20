## Requirements

The following instructions assume you have Python 3 and Docker installed. On Debian 10 run :

    sudo apt install pipenv

## Prepare development environment

This project needs [Ansible](https://www.ansible.com/), [YAMLlint](https://yamllint.readthedocs.io/en/stable/), [Ansible-lint](https://github.com/ansible/ansible-lint)
and [Molecule](https://molecule.readthedocs.io/en/stable/).

The best and easiest way to install those dependencies is to use [`pipenv`](https://pipenv.pypa.io).

    pipenv install
    pipenv shell
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

Integration tests are executed by Molecule using [Jeff Geerling's](https://www.jeffgeerling.com/) Docker images. Any `docker-xxx-ansible` images listed on his
profile on [Docker Hub](https://hub.docker.com/u/geerlingguy/) can be used with the `xxx` identifier passed as the `MOLECULE_DISTRO` environment variable. For
instance, to run the integration tests on CentOS 8:

    cd ansible_collections/marcwrobel/assertions
    MOLECULE_DISTRO=debian9 molecule test

The default distribution is `debian10`.

If you want to launch integration tests on multiple distributions :

    cd ansible_collections/marcwrobel/assertions
    for distro in debian9 debian10; do
        MOLECULE_DISTRO=$distro molecule test
    done

## Run integration tests during the development lifecycle

During the development lifecycle you may prefer to keep the docker containers running and run `molecule` commands individually:

    # Creates and configures instances
    molecule converge

    # Runs automated tests against instances
    molecule verify

    # Runs the converge step a second time and check that no tasks are marked as changed
    molecule idempotence

## Continuous integration

The GitHub Action workflow [`CI`](https://github.com/marcwrobel/ansible-collection-assertions/actions?query=workflow%3ACI) is executed for each commit, on merge
request (targeting the `main` branch) and at least once a week on saturday morning. This workflow runs :

- linting with YAMLlint and Ansible-lint,
- integration tests on collections with Molecule.
