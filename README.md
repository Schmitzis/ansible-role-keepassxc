KeePassXC
=========

Installs and configures KeePassXC for the user.

Requirements
------------

The following collections are required:

- community.general

They can be installed by running `ansible-galaxy collection install $COLLECTION`.

To include this role in your `requirements.yml` file, add the following list item:

```yaml
---
roles:
  - name: whalej84.keepassxc
    src: https://github.com/WhaleJ84/ansible-role-keepassxc.git
    scm: git

collections:
  - community.general
```

Role Variables
--------------

See *'defaults/main.yml'* or run `egrep '^[[:alpha:]_]*:' defaults/main.yml| cut
-f1 -d:` for plain list.

| Name | Type | Description | Default |
| ---- | ---- | ----------- | ------- |
| theme | string | A lowercase value of [auto, light, dark, classic] to state what theme the application should launch in | "auto" |
| compact\_mode | string | A lowercase boolean value of [true, false] to state whether the application will use the compact interface | "false" |

Example Playbook
----------------

This example playbook shows how I would use this role, with custom variables to suit my needs.

```yaml
---
- hosts: localhost

  roles:
    - role: whalej84.keepassxc
      vars:
        theme: "light"
        compact_mode: "true"
      tags: [ keepassxc ]
```
