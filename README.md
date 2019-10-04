GPG Import
=========

Use this role to import PGP keypairs into a host.
 

Role Variables
--------------

Check [./defaults/main.yaml](./defaults/main.yaml) for default values for Ansible variables. The following variables are required for the role to run:

 - `gpg_user`: The user to run the import using
 - `gpg_group`: The system group that should own imported files
 - `gpg_private_key`: Path in your playbooks to fetch the PGP private key
 - `gpg_public_key`: Path in your playbooks to fetch the PGP public key
 - `gpg_trust_file`: Path in your playbooks containing the exported trust to grant the imported keypair

Example Playbook
----------------

Playbook to import a PGP keypair might look like:

    - name: Import PGP Keys
      hosts: all
          gpg_user: "ubuntu"
          gpg_group: "ubuntu"
          gpg_private_key: "files/pgp/priv.key"
          gpg_public_key: "files/pgp/pub.key"
          gpg_trust_file: "files/pgp/ultimate.trust"
      roles:
        - role: gpg-import

License
-------

This project is released under the Apache 2 license. Read the [LICENSE](./LICENSE) file for more details.

Authors
-------

Update by [Ona Engineering](https://ona.io)
