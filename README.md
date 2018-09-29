# Ansible Role: Varnish Cache

Installs [Varnish Cache](https://varnish-cache.org) version 4.1 on RHEL / CentOS 7 or 6. Currently this role installs a multi-instance setup, disabling the `varnish` service, and replacing it with `varnish-data` by default.

## Requirements

* geerlingguy.repo-epel

## Role Variables

See `defaults/main.yml` for a list of variables available to customize the service.

## Example Usage

* Single `prod` varnish instance setup:

        - varnish

* Double varnish instance setup:

        - { role: varnish, varnish_instance: { name: prod, port: 6081, admin_port: 6082 }}
        - { role: varnish, varnish_instance: { name: stage, port: 6091, admin_port: 6092 }}

## License

This work is licensed under the MIT license. See LICENSE file for details.

## Author Information

This role was created in 2017 by [David Alger](http://davidalger.com/).
