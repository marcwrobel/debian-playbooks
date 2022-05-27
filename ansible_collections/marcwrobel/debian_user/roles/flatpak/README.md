# flatpak

Install [flatpak](https://www.flatpak.org/) packages.

Flatpak is a utility for software deployment and package management for Linux. It is advertised as offering a sandbox environment in which users can run application software in isolation from the rest of the system.

All remotes and packages are installed as user.

## Requirements

Flatpak must be installed.

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
