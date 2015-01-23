# ansible-zabbix-agentt

Install/configure zabbix agent

## Requirements

None.

## Role Variables

* ``zabbix_server_name``: Configure Zabbix server name (string, default: ``""``, **mandatory**)
* ``zabbix_server_ip``: Configure Zabbix server name (string, default: ``""``, **mandatory**)
* ``zabbix_customer_name``: Configure Zabbix customer name (string, default: ``""``, **mandatory**)
* ``zabbix_customer_hash``: Configure Zabbix customer authentication hash (string, default: ``""``, **mandatory**)
* ``zabbix_install_mysql``: Configure to manage MySQL monitoring with Zabbix (boolean, default: ``false``)
* ``zabbix_log_directory``: Configure Zabbix log directory (string, default: ``/var/log/zabbix``)
* ``zabbix_run_directory``: Configure Zabbix run directory (string, default: ``/var/run/zabbix``)

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
         - { role: ansible-zabbix-agent }

## License

Apache Version 2.0

## Integration testing

This role provides integration tests using the Ruby RSpec/serverspec framework
with a few drawbacks at the time of writing this documentation.

- Currently supports ansible_os_family == 'Debian' only.

Running integration tests requires a number of dependencies being
installed. As this role uses Ruby RSpec there is the need to have
Ruby with rake and bundler available.

    # install role specific dependencies with bundler
    bundle install

<!-- -->

    # run the complete test suite with Docker
    rake suite

<!-- -->

    # run the complete test suite with Vagrant
    RAKE_ANSIBLE_USE_VAGRANT=1 rake suite


## Author information

* Ruslan Tumarkin @ruslan.tumarkin silpion.de
* Mark Kusch @mark.kusch silpion.de


<!-- vim: set nofen ts=4 sw=4 et: -->
