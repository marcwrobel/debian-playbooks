# apache_server

Install the [Apache HTTP Server](https://httpd.apache.org/).

The `*_available` / `*_enable` configuration scheme, traditionally used on Debian, has not been
adopted by this role to avoid as much as possible Ansible-unmanaged configurations (and also because
`community.general.apache2_*` modules are really slow). Those directories are deleted by this role
to avoid misinterpretations.

Mandatory modules are:

- [mpm_event_module](https://httpd.apache.org/docs/2.4/mod/event.html) (this role is promoting
  scalability over compatibility with older software),
- [authz_core_module](https://httpd.apache.org/docs/2.4/mod/mod_authz_core.html) (required by
  authz_host_module),
- [authz_host_module](https://httpd.apache.org/docs/2.4/mod/mod_authz_host.html) (required to set
  the default security model).

Optional modules are:

- [alias_module](https://httpd.apache.org/docs/2.4/mod/mod_alias.html),
- [auth_basic_module](https://httpd.apache.org/docs/2.4/mod/mod_auth_basic.html),
- [authn_file_module](https://httpd.apache.org/docs/2.4/mod/mod_authn_file.html),
- [authz_user_module](https://httpd.apache.org/docs/2.4/mod/mod_authz_user.html),
- [deflate_module](https://httpd.apache.org/docs/2.4/mod/mod_deflate.html),
- [dir_module](https://httpd.apache.org/docs/2.4/mod/mod_dir.html),
- [env_module](https://httpd.apache.org/docs/2.4/mod/mod_env.html),
- [filter_module](https://httpd.apache.org/docs/2.4/mod/mod_filter.html),
- [mime_module](https://httpd.apache.org/docs/2.4/mod/mod_mime.html).

See _Role Variables_ to know whether those modules are enabled by default.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    # Whether Apache must be installed (`present`) or not (`absent`).
    apache_server__state: 'absent'
    apache_server__bindings:
    - name: 'localhost'
      ip: '127.0.0.1'
      ports: [80]
    apache_server__ulimit_max_files: 65536
    apache_server__arguments: ''
    apache_server__mpm_event_start_servers: 2
    apache_server__mpm_event_min_spare_threads: 25
    apache_server__mpm_event_max_spare_threads: 75
    apache_server__mpm_event_thread_limit: 64
    apache_server__mpm_event_threads_per_child: 25
    apache_server__mpm_event_max_request_workers: 150
    apache_server__mpm_event_max_connections_per_child: 0
    apache_server__alias_module_enabled: false
    apache_server__auth_basic_module_enabled: false
    apache_server__authn_file_module_enabled: false
    apache_server__authz_user_module_enabled: false
    apache_server__deflate_module_enabled: true
    apache_server__dir_module_enabled: true
    apache_server__env_module_enabled: false
    apache_server__filter_module_enabled: true
    apache_server__mime_module_enabled: true
    apache_server__mime_module_types: {}
    apache_server__mime_module_languages: {}
    apache_server__mime_module_charsets: {}

See `defaults/main.yml` for more information.

## Usage

    - hosts: desktop
      roles:
        - role: 'marcwrobel.debian_apache.apache_server'

## Links

None.
