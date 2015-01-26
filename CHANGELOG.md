# 0.4.0

Mark Kusch (8):

* s/client/agent/g
* Do not log sensible information with Ansible
* ansible-generator: Update TDD to work with Serverspec 2.N
* Do not require the playbook to configure sudo: yes
* Add support to configure rsyslog for zabbix system log capabilities

# 0.3.5

Ruslan Tumarkin (2):

* fixed security bug, removed zabbix from root group, fixed mysql check bug
* ansible-zabbix-client 0.3.5: fixed security bug, removed zabbix from root group, fixed mysql bug

# 0.3.4

Mark Kusch (1):

* Run apt update ONLY when changing repo data

# 0.3.3

Ruslan Tumarkin (1):

* Allow Zabbix to monitor MySQL (Debian)

# 0.3.2

Mark Kusch (1):

* Ensure all required directories are getting installed

# 0.3.1

Mark Kusch (1):

* Fix zabbix customer key/hash variable names

# 0.3.0

Mark Kusch (1):

* Provide more variables to better control installation of zabbix agent

# 0.2.1/0.2.2

Mark Kusch (2):

* zabbix-agent will not start if it cannot access configured log file directory
* zabbix-agent will not start if there is no file .conf in Include directory

# 0.2.0

Mark Kusch (1):

* Make a re-usable role for zabbix-agent

# 0.1.1

Mark Kusch (1):

* Fix initial installation of zabbix agent

# 0.1.0

Ruslan Tumarkin (N):

* Initial release

# 0.0.1

* Initial commit


<!-- vim: set nofen ts=4 sw=4 et: -->
