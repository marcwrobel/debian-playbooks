# apt

Configures the APT package manager :
- basic configuration (dpkg, repositories...),
- auto-upgrade with `UnattendedUpgrades`,
- changelogs with `apt-listchanges`.

Backports are always enabled because only manually installed older packages are upgraded to newer ones from backports.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    apt__install_recommends: false
    apt__mail_to: '{{ root_email }}'
    apt__mail_report: 'only-on-error'
    apt__extra_repositories: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      roles:
        - role: 'marcwrobel.debian_basics.apt'
          vars:
            apt__extra_repositories:
              - name: 'virtualbox'
                key_url: 'https://www.virtualbox.org/download/oracle_vbox_2016.asc'
                key_format: 'asc'
                repo: "deb [arch=amd64 signed-by=/usr/share/keyrings/virtualbox.asc] https://download.virtualbox.orgvirtualbox/debian {{ ansible_distribution_release }} contrib"
                state: 'present'

## Links

- [UnattendedUpgrades](https://wiki.debian.org/UnattendedUpgrades)
