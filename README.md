# nomad-cluster-playbook

This playbook deploys cluster of Consul and Nomad. Cluster consists of 3 nodes of Consul server, 3 servers of Nomad and 3 clients of Nomad. Also it deploys docker-ce as a driver for Nomad.

Vault file password: 3224
 - create sudouses in each server and add password to it. Change vault file and nomad_inv.txt 
 - change host name to unique
 - change /consul/templates/config.json "start join" block to the actual IP addresses of the servers.

Command for ping: 
ansible nomad -m ping -i nomad_inv.txt --ask-vault-pass --extra-vars '@nomad_pass.yml' -v

Command for run:
ansible-playbook cluster_playbook.yml -i nomad_inv.txt --ask-vault-pass --extra-vars '@nomad_pass.yml' -v
