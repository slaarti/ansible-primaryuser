# User Role

Super simple ansible role to create a user on a system, and optionally
provide SSH authorized keys.

This is just basically a parameterized role wrapper around some built-in
ansible modules.

Role Variables
--------------

    username: ""

The user's username. If left empty, nothing happens.

    realname: ""

Sets the user's comment field, which is typically the real name.

    password: ""

The user's crypted password.

    shell: "/bin/bash"

The user's shell.

    groups: "sudo"

A comma-separated list of additional non-user-specific groups to add the
user to. By default, gives `sudo` privileges. If you want that and
additional groups besides, make sure to include `sudo` in the list.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: slaarti.user
           username: "testuser"
           realname: "Ralph Testes"
           password: "12345"

License
-------

Unlicense; see the LICENSE file.

Author Information
------------------

Chris Pinard <slaarti@gmail.com>