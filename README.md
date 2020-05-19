# Ansible apache role

This is an [Ansible](http://www.ansible.com) role which intall a basic httpd server.

## Requirements

[Ansible 2.9+](http://docs.ansible.com/ansible/latest/intro_installation.html)

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

A list of modules can be passed in apache_aditional_modules list. Only ssl module
is configured. Other modules are installed with defaults.

This role performs a basic configuration. For custom settings you can add .conf
files in the conf.d directory inside the apache configuration directory.

This role provide a vhost.d directory inside the apache configuration directory
to store your vhost configurations,

SSL global and vhost custom directives variables are supplied, witch are filled with raw text format.

SSLProtocol force TLSv1.2 negotiation for Fedora 29+ compatibility as it uses version 1.1.1 of openssl.
Adjust the SSLProtocol and SSLCipherSuite according to your needs and your certificates and keys.

## Dependencies


- [amtega.check_platform](https://galaxy.ansible.com/amtega/check_platform)
- [amtega.packages](https://galaxy.ansible.com/amtega/packages)

## Usage


This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - role: amtega.apache

```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.apache/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2020 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
