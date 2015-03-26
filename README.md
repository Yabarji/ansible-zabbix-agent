# ansible-zabbix-agent

Install/configure zabbix agent

## Requirements

None.

## Role Variables

* ``zabbix_agent_server_name``: Configure Zabbix server name (string, default: ``""``, **mandatory**)
* ``zabbix_agent_server_ip``: Configure Zabbix server name (string, default: ``""``, **mandatory**)
* ``zabbix_agent_customer_name``: Configure Zabbix customer name (string, default: ``""``, **mandatory**)
* ``zabbix_agent_customer_hash``: Configure Zabbix customer authentication hash (string, default: ``""``, **mandatory**)
* ``zabbix_agent_user_name``: Configure service user to run Zabbix as (string, default: ``zabbix``)
* ``zabbix_agent_user_group``: Configure service group to run Zabbix as (string, default: ``zabbix``)
* ``zabbix_agent_allow_restart``: Whether to allow to automatic restart the zabbix agent (boolean, default: ``true``)
* ``zabbix_agent_log_directory``: Configure Zabbix log directory (string, default: ``/var/log/zabbix``)
* ``zabbix_agent_run_directory``: Configure Zabbix run directory (string, default: ``/var/run/zabbix``)

### MySQL configuration

* ``zabbix_agent_mysql_enable``: Configure to manage MySQL monitoring with Zabbix (boolean, default: ``false``)
* ``zabbix_agent_mysql_user``: Configure user for zabbix to connect to the MySQL server (string, default: ``zabbix``)
* ``zabbix_agent_mysql_pass``: Configure password for user to connect to the MySQL server (string, default: ``""`` **MANDATORY**)
* ``zabbix_agent_mysql_login_host``: Configure MySQL server host address (string, default: ``127.0.0.1``)
* ``zabbix_agent_mysql_login_port``: Configure MySQL server host port (integer, default: ``3306``)

### Syslog configuration

* ``zabbix_agent_syslog_enable``: Configure to manage Syslog for monitoring with Zabbix (boolean, default: ``false``)
* ``zabbix_agent_allow_restart_rsyslog``: Whether to allow automatic restarts the syslog server (boolean, default: ``true``)
* ``zabbix_agent_syslog_configuration``: Configure Syslog events to store in {{ zabbix_agent_syslog_zabbix_logfile }} (string, default: ``""``)
* ``zabbix_agent_syslog_zabbix_logfile``: Configure Syslog where to put data for Zabbix to fetch (string, default: ``/var/log/zabbix.log``)

### Postfix configuration

* ``zabbix_agent_postfix_enable``: Configure to manage Postfix for monitoring with Zabbix (boolean, default: ``false``)

### Apache2 configuration

* ``zabbix_agent_apache2_enable``: Configure to manage Apache2 for monitoring with Zabbix (boolean, default: ``fa    lse``)

#### zabbix_agent_syslog_configuration

Allows to configure rsyslog for facilities and log level. e.g.

    *.err;auth.none;auth.crit

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
         - { role: ansible-zabbix-agent }

## TODOs

* Verify rsyslog with syslog.yml.
  * Fixup rsyslog management completely.
* Install log rotation configuration with syslog.yml.

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
