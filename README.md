letsencrypt
===========

![Lint Code Base](https://github.com/jkirk/ansible-role-base/actions/workflows/linter.yml/badge.svg)
![Ansible Molecule](https://github.com/jkirk/ansible-role-base/actions/workflows/molecule.yml/badge.svg)

A simple role to deploy [Dehydrated](https://github.com/dehydrated-io/dehydrated), a client for signing certificates with an ACME-server (e.g. Let's Encrypt).

Requirements
------------

None.

Role Variables
--------------

* letsencrypt_domains: Set the domain(s) and its optional aliases to be served by Let's Encrypt.
* (optional) letsencrypt_dehydrated_version: Set the version to be used for [Dehydrated](https://github.com/dehydrated-io/dehydrated/releases), defaults to 'v0.7.1'.

Dependencies
------------

None.

Example Playbook
----------------

Single domain:
```yaml
    - hosts: website
      roles:
        - { role: jkirk.letsencrypt, letsencrypt_domains: [ 'demo.example.com' ] }
```

Multiple domains:
```yaml
    - hosts: website
      roles:
        - { role: jkirk.letsencrypt, letsencrypt_domains: [ 'demo.example.com', 'demo2.example.com' ], letsencrypt_dehydrated_version: 'v0.6.2' }
```

To put domain aliases, put the alias next to the main domain:
```yaml
    - hosts: website
      roles:
        - { role: jkirk.letsencrypt, letsencrypt_domains: [ 'demo.example.com alias.example.com' ] }
```

License
-------

MIT

Author Information
------------------

Darshaka Pathirana - <https://synpro.solutions>
