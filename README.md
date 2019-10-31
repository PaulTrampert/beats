Role Name
=========

Installs filebeat and metricbeat, along with a base configuration.

Role Variables
--------------

| Variable                 | Type            | Default                            | Description                                                              |
|--------------------------|-----------------|------------------------------------|--------------------------------------------------------------------------|
| beats_version            | string          | `7.x`                              | The version of beats to install                                          |
| elasticsearch_hosts      | array[string]   | `[]`                               | Array of elasticsearch hosts to ship logs to                             |
| elasticsearch_protocol   | string          | `https|http`                       | The elasticsearch protocol to use                                        |
| elasticsearch_user       | string          | `undefined`                        | The user for basic auth w/ elasticsearch                                 |
| elasticsearch_password   | string          | `undefined`                        | The password to use to connect to elasticsearch                          |
| kibana_host              | string          | `""`                               | The hostname for kibana                                                  |
| beats_autodiscover       | string          | `undefined`                        | The provider for beats autodiscovery                                     |

Dependencies
------------

None

Example Playbook
----------------

```yml
---
- hosts: localhost
  become: yes
  vars:
    elasticsearch_hosts: ["elasticsearch.ptrampert.com:443"]
    kibana_host: "kibana.ptrampert.com"
  roles:
  - beats
```

License
-------

MIT