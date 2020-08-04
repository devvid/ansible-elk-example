Elasticsearch
=========

Configures a Elasticsearch server. Currently the default user settings have not been modified and the admin account is:

username: blah
password: blah

Requirements
------------

todo

Role Variables
------------

defaults/main.yml


Dependencies
------------

None

Example Playbook
------------

```
- name: configure and deploy the elasticsearch search engine application
  hosts: elasticsearchservers
  remote_user: david
  roles:
    - elasticsearch
      state: present
  vars:
    es_version: 7.8.0
    es_config:
      network.host: 0.0.0.0
      discovery.type: single-node
```