Role Name: sardpost.kibana4
=========

Ansible role for installing Kibana 4.5 on EL 7 platform (RHEL/Centos 7).
The role installs Kibana 4.5 from the official repository. The role uses
the default configuration files.
Features:

```yml

          Tasks:
          - Import GPG key for official repository
          - Install rpm Repository
          - Install kibana 4.5
          - Enable and start Kibana 4.5 service
```
Refer to the official documentation page for further information:

```yml
          https://github.com/elastic/kibana/blob/v4.5.0/README.md
```

Requirements
------------

```yml
        - Platform RHEL/Centos 7
        - Elasticsearch version 2.3.0 or later
        - ntpd to prevent invalid timestamps in your logs
```

Role Variables
--------------


Dependencies
------------

```yml
      - sardpost.elasticsearch
      - yaegashi.blockinfile  #not needed in Ansible 2 as part of core modules
```


Example Playbook
----------------

```yml
  - name: Install EFK stack (Elasticsearch, Fluentd, Kibana)
    hosts: test_lab
    remote_user: centos
    sudo: yes

    roles:
      - sardpost.java8
      - sardpost.elasticsearch
      - sardpost.fluentd
      - sardpost.kibana4
      - yaegashi.blockinfile
```

Version:
--------
0.1.0

License
-------
GPLv3

Author Information
------------------
Davide M. Puggioni
