# sysctl

Manage kernel parameters using sysctl.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    sysctl__shmmax: '{{ sysctl__kernel_shmmax_default }}'
    sysctl__shmall: '{{ sysctl__kernel_shmall_default }}'
    sysctl__ip_forward: false
    sysctl__default_additional_variables: {}
    sysctl__group_additional_variables: {}
    sysctl__hosts_additional_variables: {}

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      roles:
        - role: 'marcwrobel.debian_basics.sysctl'

## Links

- [The Linux Kernel documentation](https://www.kernel.org/doc/html/latest/)
- [Linux Hardening Guide - sysctl](https://madaidans-insecurities.github.io/guides/linux-hardening.html#sysctl)
- [debops.sysctl](https://github.com/debops/debops/tree/master/ansible/roles/sysctl)
- [40 Linux Server Hardening Security Tips - 2021 edition](https://www.cyberciti.biz/tips/linux-security.html)
