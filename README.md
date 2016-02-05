<img src="http://www.elao.com/images/corpo/logo_red_small.png"/>

[![Ansible Role](https://img.shields.io/ansible/role/5548.svg?style=plastic)](https://galaxy.ansible.com/list#/roles/5548) [![Platforms](https://img.shields.io/badge/platforms-debian-lightgrey.svg?style=plastic)](#) [![License](http://img.shields.io/:license-mit-lightgrey.svg?style=plastic)](#)

# Ansible Role: ACL

This role will install ACL (Access Control List) package.

It's part of the ELAO <a href="http://www.manalas.com" target="_blank">Ansible stack</a> but can be used as a stand alone component.

## Requirements

- Ansible 1.7.2+

## Dependencies

None.

## Installation

### Ansible 2+

Using ansible galaxy cli:

```bash
ansible-galaxy install elao.acl,2.0
```

Using ansible galaxy requirements file:

```yaml
- src:     elao.acl
  version: 2.0
```

### Ansible 1 (no longer maintained)

Using ansible galaxy cli:

```bash
ansible-galaxy install elao.acl,1.0
```

Using ansible galaxy requirements file:

```yaml
- src:     elao.acl
  version: 1.0
```

## Role Handlers

None

## Role Variables

| Name                | Default | Type         | Description    |
| ------------------- | ------- | ------------ | -------------- |
| `elao_acl_files`    | []      | Collection   | List of files  |


### ACL configuration

The `elao_acl_files` allow you to set file ACL informations, following options are availables.

| Name          | Default      | Type    | Description                           |
| ------------- | ------------ | ------- | ------------------------------------- |
| `name`        | ~ (required) | String  | The full path of the file or object.  |
| `default`     | ~            | Boolean | If the target is a directory, setting this to yes will make it the default acl for entities created inside the directory. It causes an error if name is a file. |
| `entity`      | ~            | String  | Actual user or group that the ACL applies to when matching entity types user or group are selected. |
| `entry`       | ~            | String  | DEPRECATED. The acl to set or remove. This must always be quoted in the form of '<etype>:<qualifier>:<perms>'.|
| `etype`       | ~            | String  | The entity type of the ACL. Can be user, group, mask or other |
| `follow`      | True         | Boolean | Whether to follow symlinks on the path if a symlink is encountered. |
| `permissions` | ~            | String  | Permissions to apply/remove can be any combination of r, w and x |
| `state`       | query        | String  | Defines whether the ACL should be present or not. The query state gets the current acl without changing it, for use in 'register' operations. Can be 'query', 'present' or 'absent'. |

## Example

```yaml
elao_acl_files:
    - name:        /etc/foo.conf
      entity:      www-data
      etype:       user
      permissions: "r"
      state:       present
```

## Example playbook
```yaml
    - hosts: servers
      roles:
         - { role: elao.acl }
```
# Licence

MIT

# Author information

ELAO [**(http://www.elao.com/)**](http://www.elao.com)
