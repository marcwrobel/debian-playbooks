# additional_facts

Set up additional [local facts](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_vars_facts.html#facts-d-or-local-facts).

Note that it is best if those scripts do not depend on specific user privileges.

## Requirements

None.

## Dependencies

None.

## Role Variables

Available variables are listed below, along with default values:

    local_facts__scripts: []

See `defaults/main.yml` for more information.

## Usage

    - hosts: servers
      roles:
        - role: 'marcwrobel.debian_common.local_facts'
          vars:
            local_facts__scripts:
              - namespace: mountpoints
                description: Get a list of all of the EXT mountpoints.
                script: jc mount | jq 'map(select(.type == ("ext2", "ext4")) | .mount_point)'
                dependencies: ['jc', 'jq']

## Links

None.
