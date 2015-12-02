elasticsearch
=============

Role which installs and configures elasticsearch.


Example
-------

```
---

# Example of how to use the role
- hosts: myhost1
  roles:
    - role: common/elasticsearch
      elasticsearch_config:
        network.bind_host: "{{ ansible_eth0.ipv4.address }}"
        http.host: "{{ ansible_eth0.ipv4.address }}"

# Example of how to configure the role
- hosts: myhost2
  roles:
    - role: common/elasticsearch
      elasticsearch_version: 1.4
      elasticsearch_config:
        # Accept only localhost connections
        network.bind_host: "127.0.0.1"
        http.host: "127.0.0.1"
```


Role variables
--------------

List of variables used by the role:

```
# Default elasticsearch configuration
elasticsearch_version: 2.x
# available versions are:
#   0.90
#   1.3
#   1.4
#   1.5
#   1.6
#   1.7
#   2.x
elasticsearch_config: {}
```


Dependencies
------------

* [`yumrepo`](https://github.com/picotrading/ansible-yumrepo) role
* [`oracle-java`](https://github.com/picotrading/ansible-oracle_java) role


License
-------

MIT


Author
------

Jiri Tyr

