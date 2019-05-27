letsencrypt
===========

[![Build Status](https://travis-ci.com/jkirk/ansible-role-letsencrypt.svg?branch=master)](https://travis-ci.com/jkirk/ansible-role-letsencrypt)

A simple role to deploy letsencrypt to a website.

Requirements
------------

None.

Role Variables
--------------

* letsencrypt_domains: Set the domain(s) and its optional aliases to be served by Let's Encrypt.
* (optional) letsencrypt_dehydrated_version: Set the version to be used for [dehydration](https://github.com/lukas2511/dehydrated/releases), defaults to 'HEAD'.

Dependencies
------------

None.

Example Playbook
----------------

Single domain:
```yaml
    - hosts: website
      roles:
        - { role: letsencrypt, letsencrypt_domains: [ 'demo.example.com' ] }
```

Multiple domains:
```yaml
    - hosts: website
      roles:
        - { role: letsencrypt, letsencrypt_domains: [ 'demo.example.com', 'demo2.example.com' ], dehydrated_version: 'v0.6.2' }
```

To put domain aliases, put the alias next to the main domain:
```yaml
    - hosts: website
      roles:
        - { role: letsencrypt, letsencrypt_domains: [ 'demo.example.com alias.example.com' ] }
```

License
-------

MIT

Author Information
------------------

Darshaka Pathirana - https://synpro.solutions
