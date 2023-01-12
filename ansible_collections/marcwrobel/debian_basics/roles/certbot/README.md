# certbot

Manage certificates using [certbot](https://certbot.eff.org/), the tool for automatically using
Let’s Encrypt certificates on administrated websites to enable HTTPS.

Certificates are obtained using the [webroot](https://eff-certbot.readthedocs.io/en/stable/using.html#webroot)
method, so be sure the `<webroot>/.well-known` directory is properly exposed. More information on
[Let’s Encrypt HTTP-01 challenge documentation](https://letsencrypt.org/docs/challenge-types/#http-01-challenge).

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    certbot__dryrun_mode: false
    certbot__test_mode: false
    certbot__certs: []
    certbot__auto_renew_frequency: 'daily'

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      collections:
        - 'marcwrobel.debian_basics'
      roles:
        - role: 'certbot'
          vars:
            certbot__certs
              - email: user@example.com
                webroot: "/var/www/html"
                domains:
                  - example.com
                  - example1.com
                  - example2.com
          tags: [ 'certbot' ]

## Links

None.
