# openssh_server

Install the [OpenSSH server](https://www.openssh.com/).

The server is configured using a [Mozilla modern configuration](https://infosec.mozilla.org/guidelines/openssh#modern-openssh-67)

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    openssh_server__myhostname: '{{ inventory_hostname }}'
    openssh_server__myorigin: '{{ inventory_hostname.split(".")[1:] | join(".") }}'
    openssh_server__mynetworks: '127.0.0.0/8 [::ffff:127.0.0.0]/104 [::1]/128'
    #openssh_server__relay_host: '<host>:<port>'
    #openssh_server__relay_login: '<login>'
    #openssh_server__relay_password: '<password>'
    openssh_server__tls_cert: '/etc/ssl/certs/ssl-cert-snakeoil.pem'
    openssh_server__tls_key: '/etc/ssl/private/ssl-cert-snakeoil.key'

See `defaults/main.yml` for more information.

## Usage

    - hosts: server
      roles:
        - role: 'marcwrobel.debian_server.openssh_server'
          vars:
            openssh_server__relay_host: '{{ my_relay_host }}'
            openssh_server__relay_login: '{{ my_relay_login }}'
            openssh_server__relay_password: '{{ my_relay_password }}'

## Regenerating moduli

You can use this script to regenerate `/etc/ssh/moduli`:

```shell
echo '# Time Type Tests Tries Size Generator Modulus' > moduli
for bits in 4096 6144 7680 8192; do
  ssh-keygen -M generate -O bits="$bits" "moduli-$bits.candidates"
  ssh-keygen -M screen -f "moduli-$bits.candidates" "moduli-$bits"
done
```

## Links

None.
