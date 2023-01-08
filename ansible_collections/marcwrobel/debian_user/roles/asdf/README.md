# asdf

Install [asdf](https://asdf-vm.com/).

asdf is a tool version manager.

## Requirements

`curl` and `git` must be available.

Note that each plugin have their own dependencies too.
See https://asdf-vm.com/guide/getting-started.html#plugin-dependencies.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    asdf__repository_url: 'https://github.com/asdf-vm/asdf.git'
    asdf__version: 'v0.10.1'
    asdf__directory: '{{ ansible_env.HOME }}/.asdf'
    asdf__plugins: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: desktop
      roles:
        - role: 'marcwrobel.debian_user.asdf'

## Links

None.
