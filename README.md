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
| start\_only\_a\_single\_</br>instance\_of\_keepassxc | string | A lowercase boolean value of [true, false] to state whether more than one instance can launch | "true" |
| automatically\_launch\_keepassxc</br>\_at\_system\_startup | string | A lowercase boolean value of [true, false] to state whether KeepassXC will launch at boot | "false" |
| minimize\_instead\_of\_app\_exit | string | A lowercase boolean value of [true, false] to state whether to minimize the application on close | "false" |
| show\_a\_system\_tray\_icon | string | A lowercase boolean value of [true, false] to state whether to show a system tray icon | "false" |
| tray\_icon\_type | string | A lowercase value of [monochrome-light, monochrome-dark, colorful] to state what colors the tray icon should use | "monochrome-light" |
| enable\_browser\_integration | string | A lowercase boolean value of [true, false] to state whether browser integration is enabled | "false" |
| enable\_ssh\_agent\_integration | string | A lowercase boolean value of [true, false] to state whether to enable the SSH agent | "false" |

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
        automatically_launch_keepassxc_at_system_startup: "true"
        minimize_instead_of_app_exit: "true"
        show_a_system_tray_icon: "true"
        tray_icon_type: "colorful"
        enable_browser_integration: "true"
        enable_ssh_agent_integration: "true"
      tags: [ keepassxc ]
```
