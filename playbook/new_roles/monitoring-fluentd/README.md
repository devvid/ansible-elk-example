Fluentd
=========

Configures a Fluentd server on all nodes storing logging data to the elasticsearch datastorage within the local network. Currently the default user settings have not been modified and the admin account is:

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
- name: configure and deploy the fluentd driver on all servers to route logs to elasticsearch
  hosts: all
  roles:
    - fluentd
      state: present
```