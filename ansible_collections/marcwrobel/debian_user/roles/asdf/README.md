# flatpak

Install [asdf](https://asdf-vm.com/).

asdf is a tool version manager.

## Requirements

`curl` and `git` must be available.

Note that each plugin have their own dependencies too. See https://asdf-vm.com/guide/getting-started.html#plugin-dependencies.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    flatpak__remotes: []
    flatpak__apps: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: desktop
      roles:
        - role: 'marcwrobel.debian_user.flatpak'

## Links

- [Debian Quick Setup](https://flatpak.org/setup/Debian)
