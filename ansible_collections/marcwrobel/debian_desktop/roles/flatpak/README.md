# flatpak

Install [flatpak](https://www.flatpak.org/) and configure remotes.

Flatpak is a utility for software deployment and package management for Linux. It is advertised as offering a sandbox environment in which users can run application software in isolation from the rest of the system.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    flatpak__system_remotes_group: []
    flatpak__system_remotes_host: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      roles:
        - role: 'marcwrobel.debian_desktop.flatpak'

## Links

- [Debian Quick Setup](https://flatpak.org/setup/Debian)
