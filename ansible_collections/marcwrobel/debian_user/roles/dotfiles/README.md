# flatpak

Configure a user [dotfiles](https://wiki.archlinux.org/title/Dotfiles).

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    # dotfiles__repository: 'https://github.com/marcwrobel/dotfiles.git'
    dotfiles__remove_existing_files: false

See `defaults/main.yml` for more information.

## Usage

    - hosts: desktop
      roles:
        - role: 'marcwrobel.debian_user.dotfiles'

## Links

- [Dotfiles](https://wiki.archlinux.org/title/Dotfiles)
