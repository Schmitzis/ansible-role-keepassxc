KeePassXC
=========

Installs and configures KeePassXC for the user.

Requirements
------------

The following collections are required:

- community.general

They can be installed by running `ansible-galaxy collection install $COLLECTION`.

Role Variables
--------------

See *'defaults/main.yml'* or run `egrep '^[[:alpha:]_]*:' defaults/main.yml| cut
-f1 -d:` for plain list.

Example Playbook
----------------

    - hosts: localhost
      roles:
         - { role: whalej84.keepassxc, theme: "dark" }

