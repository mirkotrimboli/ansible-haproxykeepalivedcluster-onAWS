# ansible-haproxykeepalivedcluster-onAWS
Delivery an HAproxy cluster with keepalived for manage VIP on AWS

# AWS prerequisites
Make sure that the AWS environment has:

* Service Group with open Inbound rules for SSH connection
* that an ip was given to the primary network card
* that a NetworkInterface not associated with any node has been created

On the Ansible server:

* Download with git clone
* Inside the inventory path insert the "key.pem" for access in SSH
* Modify the hosts file of the ansible server by adding the ip of the hosts to reach and naming them as specified in keeproxy.hosts

# Installation and initial configuration of the nodes

* check the variable in group_vars / all / vars.yml
* if necessary change the values of the variables according to your environment

launch the ansible playbook with the command:

* ansible-playbook -i keeproxy.hosts keeproxy.yml --key-file=./chiave.pem --user=centos
