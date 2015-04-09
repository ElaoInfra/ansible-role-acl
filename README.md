<img src="http://www.elao.com/images/corpo/logo_red_small.png"/>

# Ansible Role: ACL repositories

This role will install ACL (Access Control List) package.

It's part of the ELAO [Ansible stack](http://ansible.elao.com) but can be used as a stand alone component.

## Requirements

- Ansible 1.7.2+

## Dependencies

None.

## Installation

Using ansible galaxy:

```bash
ansible-galaxy install elao.acl
```

## Role Handlers

None

## Role Variables

None

## Example playbook

    - hosts: servers
      roles:
         - { role: elao.acl }

# Licence

MIT

# Author information

ELAO [**(http://www.elao.com/)**](http://www.elao.com)
