Python app using logger to output to a network ip (Fluentd)
Application and system logs.

# Development
Ansible scripts to setup the remote host server, creating 8 virtual machines each running a different config.
Node = Server

- Management server
    - Ansible script runs from here, connects to the remote servert and setups up KVM/virtual machines.

- Remote A host server (KVM)
    - Node 1
        - Test&&& Application
        - Kubaneties cluster
        - Fluentd (Connects to Node 3)
        192.168.1.21
    - Node 2
        - Kabana (GUI)
        - Fluentd (Connects to Node 3)
        192.168.1.22
    - Node 3
        - Elasticsearch (DB)
        - Fluentd (Connects to Node 3/Local)
        192.168.1.23
        

# Steps
1. Install Gogs.io selft hosted Git repository. Note: May not be required
2. Run ansible script
    - Connect to remote server
    - Delete all KVM virtual machines
    - Startup 8x servers using a Ubuntu image
    - SSH into all nodes and install software


# Testing
Kibana URL
http://192.168.1.22:5601


# Observations

[Installing elasticsearch] Error regarding locked file when installing eleasticsearch repository (debian: Install apt-transport-https to support https APT downloads)

[CentOS installed]

[Elasticsearch] role works out of box but may need to be trimed of fat. Note to bind ip address to 0.0.0.0
[Elasticsearch] Also; Need to allow 9200 tcp/udp through the firewall and then reload then works. firewall-cmd

[Fluentd] Finally managed to get installed; [TODO] Configure firewall to allow apps to function 