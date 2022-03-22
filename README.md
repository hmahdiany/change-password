# Change Passowrd
This project is an Ansible role for either creating or resetting a password for a single user.
If the username which is specified in `group_vars/nodes/username.yaml` does not exist, this role will create that user and set password for it. If the username already exists this role will reset password for that user.

New passwords will be stored in `passwords/{{ inventory_hostname }}-latest` file. `{{ inventory_hostname }}` is the node name that is specified in `inventory.ini`. Before resetting password first the latest password will be archived in `passwords/archive/{{ inventory_hostname }}`.