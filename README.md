# Ansible apache role

This is an [Ansible](http://www.ansible.com) role to intall a basic httpd server.

The role performs a basic configuration. For custom settings you can add .conf
files in apache conf.d directory.

The role provide a vhost.d directory inside the apache configuration directory
to store your vhost configurations.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

SSL global and vhost custom directives variables are supplied, witch are filled with raw text format.

SSLProtocol force TLSv1.2 negotiation for Fedora 29+ compatibility as it uses version 1.1.1 of openssl.

Adjust the SSLProtocol and SSLCipherSuite according to your needs and your certificates and keys.

## Usage

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - role: amtega.apache

```

## Testing

Tests are based on [molecule with docker containers](https://molecule.readthedocs.io/en/latest/installation.html).

```shell
cd amtega.apache

molecule test
```

## License

Copyright (C) 2020 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
- Juan Antonio Valiño García
