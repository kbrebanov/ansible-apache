[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)

apache
======

Installs and configures Apache.

Requirements
------------

This role requires Ansible 1.4 or higher.

Role Variables
--------------

| Name                          | Default | Description                                                                                |
|-------------------------------|---------|--------------------------------------------------------------------------------------------|
| apache_port                   | 80      | Port Apache will listen on for HTTP requests                                               |
| apache_ssl_port               | 443     | Port Apache will listen on for HTTPS requests                                              |
| apache_timeout                | 300     | The number of seconds before receives and sends time out                                   |
| apache_keepalive              | 'On'    | Whether or not to allow persistent connections                                             |
| apache_max_keepalive_requests | 100     | The maximum number of requests to allow during a persistent connection                     |
| apache_keepalive_timeout      | 5       | Number of seconds to wait for the next request from the same client on the same connection |
| apache_hostname_lookups       | 'Off'   | Log the names of clients or just their IP addresses                                        |

Dependencies
------------

None

Example Playbook
----------------

Install Apache
```
- hosts: all
  roles:
    - { role: kbrebanov.apache }
```

Install Apache and specify HTTP port to listen on
```
- hosts: all
  roles:
    - { role: kbrebanov.apache, apache_port: 8000 }
```

Install Apache and enable hostname lookups
```
- hosts: all
  roles:
    - { role: kbrebanov.apache, apache_hostname_lookups: 'On' }
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
