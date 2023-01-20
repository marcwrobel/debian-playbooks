# openssh_server

Install the [OpenSSH server](https://www.openssh.com/).

The server is configured using a [Mozilla modern configuration](https://infosec.mozilla.org/guidelines/openssh#modern-openssh-67)

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    openssh_server__listen_addresses: ['{{ ansible_default_ipv4.address }}:22']
    openssh_server__host_keys:
    - type: 'ed25519'
      size: '0'
    - type: 'ecdsa'
      size: '256'
    - type: 'rsa'
      size: '4096'

See `defaults/main.yml` for more information.

## Usage

    - hosts: server
      roles:
        - role: 'marcwrobel.debian_server.openssh_server'
          vars:
            openssh_server__listen_addresses: ['127.0.0.1:22']

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
