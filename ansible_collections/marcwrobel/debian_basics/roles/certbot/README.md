# certbot

Manage certificates using [certbot](https://certbot.eff.org/), the tool for automatically using
Let’s Encrypt certificates on administrated websites to enable HTTPS.

Certificates are obtained using the [webroot](https://eff-certbot.readthedocs.io/en/stable/using.html#webroot)
method, so be sure the `<webroot>/.well-known` directory is properly exposed.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    N/A

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      collections:
        - 'marcwrobel.debian_basics'
      roles:
        - role: 'certbot'
          vars:
            N/A
          tags: [ 'certbot' ]

## Links

None.
