# postfix_satellite

Install the [postfix SMTP client](https://marlam.de/postfix/) as a mail transfer agent, also known
as [null client](https://www.postfix.org/STANDARD_CONFIGURATION_README.html#null_client).

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    postfix_satellite__state: 'absent'
    postfix_satellite__myhostname: '{{ inventory_hostname }}'
    postfix_satellite__myorigin: '{{ inventory_hostname.split(".")[1:] | join(".") }}'
    postfix_satellite__mynetworks: '127.0.0.0/8 [::ffff:127.0.0.0]/104 [::1]/128'
    #postfix_satellite__relay_host: '<host>:<port>'
    #postfix_satellite__relay_login: '<login>'
    #postfix_satellite__relay_password: '<password>'
    postfix_satellite__tls_cert: '/etc/ssl/certs/ssl-cert-snakeoil.pem'
    postfix_satellite__tls_key: '/etc/ssl/private/ssl-cert-snakeoil.key'

See `defaults/main.yml` for more information.

## Usage

    - hosts: server
      roles:
        - role: 'marcwrobel.debian_server.postfix_satellite'
          vars:
            postfix_satellite__state: 'present'
            postfix_satellite__relay_host: '{{ my_relay_host }}'
            postfix_satellite__relay_login: '{{ my_relay_login }}'
            postfix_satellite__relay_password: '{{ my_relay_password }}'

## Links

- http://www.postfix.org/postconf.5.html
- http://www.postfix.org/STANDARD_CONFIGURATION_README.html#null_client
- https://www.linuxbabe.com/debian/configure-postfix-smtp-relay-mailjet
- https://www.mail-tester.com
