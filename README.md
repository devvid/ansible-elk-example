Python app using logger to output to a network ip (Fluentd)
Application and system logs.


3x locations wih options.

1. Remote A;
fluentd
    - op system logs
    - database logs
    - authentication logs
    - application(Python, C++ apps) logs
elasticsearch

2. Remote B;
fluentd
    - op system logs
    - database logs
    - authentication logs
    - application(Python, C++ apps) logs
elasticsearch

3. Local;
fluentd
    - op system logs
    - database logs
    - authentication logs
    - application(Python, C++ apps) logs
elasticsearch
kibana
    - Connects to Remote A elasticsearch
    - Connects to Remote B elasticsearch
    - Connects to Local elasticsearch


# Development
Ansible scripts to setup the remote host server, creating 8 virtual machines each running a different config.
Node = Server

- Management server
    - Ansible script runs from here, connects to the remote servert and setups up KVM/virtual machines.

- Remote A host server (KVM)
    - Node 1
        - Kubaneties cluster
        - Fluentd (Connects to Node 3)
        192.168.1.17
    - Node 2
        - Kabana (GUI)
        - Fluentd (Connects to Node 3)
        192.168.1.18
    - Node 3
        - Elasticsearch (DB)
        - Fluentd (Connects to Node 3/Local)
        192.168.1.20
        


# Steps
1. Install Gogs.io selft hosted Git repository. Note: May not be required
2. Run ansible script
    - Connect to remote server
    - Delete all KVM virtual machines
    - Startup 8x servers using a Ubuntu image
    - SSH into all nodes and install software


# Testing
Kibana URL
http://192.168.1.18:5601


# Observations

[Installing elasticsearch] Error regarding locked file when installing eleasticsearch repository (debian: Install apt-transport-https to support https APT downloads)