Kibana
=========

Configures a Kibana server connecting to elasticsearch datastorage within the local network. Currently the default user settings have not been modified and the admin account is:

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
- name: configure and deploy the kibana GUI interface application
  hosts: kibanaservers
  roles:
    - kibana
      state: present
```