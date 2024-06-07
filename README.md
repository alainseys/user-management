Usermanagement
=========

This role will create users and update their password when needed.

Requirements
------------

You should have the ssh_keys directory on the same level where the playbook is been exectued. The ssh keys should be in this directory and the username should be in the public keys filename.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

    - name: Create users
      ansible.builtin.includ_role:
        name: linux/user-management
      vars:
        users:
         - username: testaccount
           password: $6$EDqRN3xiI3daSv3b$YfdVlAgy6aMGGrUiPkN20Agw6CTi/WT.gPVXzIUit5rz23a6Zzj3k.NS9JuYQ5MYlKZpT6/mcEJZkvB.e.He3.
           update_password: always
           shell: /bin/bash
           ssh_key: "{{ lookup('file','ssh_keys/testaccount.pub') }}"
           use_sudo: true
           groups: docker, wheel
           servers:
            - all

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
