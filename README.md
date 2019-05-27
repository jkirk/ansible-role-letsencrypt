letsencrypt
===========

A simple role to deploy letsencrypt to a website.

Requirements
------------

None.

Role Variables
--------------

* domains: Set the domain(s) and its optional aliases to be served by Let's Encrypt.

Dependencies
------------

None.

Example Playbook
----------------

Single domain:
```yaml
    - hosts: website
      roles:
        - { role: letsencrypt, domains: [ 'demo.example.com' ] }
```

Multiple domains:
```yaml
    - hosts: website
      roles:
        - { role: letsencrypt, domains: [ 'demo.example.com', 'demo2.example.com' ] }
```

To put domain aliases, put the alias next to the main domain:
```yaml
    - hosts: website
      roles:
        - { role: letsencrypt, domains: [ 'demo.example.com alias.example.com' ] }
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
