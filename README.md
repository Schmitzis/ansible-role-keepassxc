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

Too many to list here.
See `defaults/main.py`.

Example Playbook
----------------

    - hosts: localhost
      roles:
         - { role: whalej84.keepassxc, theme: "dark" }

