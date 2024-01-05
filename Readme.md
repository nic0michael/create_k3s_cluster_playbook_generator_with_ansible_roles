**The instructions for using this project can be found here** \
http://rino.kozow.com/devops/posts/create-k3s-cluster-ansible-playbook/ \
On this page, we will provide a link to our YouTube video with instructions for creating this on your Proxmox Homelab

**The Video showing how to do this** \
https://youtu.be/ZD6X-lFsGiw


We provide you with two options:
1. Run the playbooks using commands from the terminal and values in the Inventory file and pass them as variables
2. Using Semaphore to automate this process from the Browser
Instructions are provided for both options

## 1. Running the create_k3s_primary_master_node.yml Playbook
If you want to run the  create_k3s_primary_master_node.yml from the terminal \
Run this command
```
ansible-playbook playbooks/create_primary_master_node.yml \
  -i inventories/production/hosts.ini \
  -e "node_name=tiger.loseyourip.com" \
  -e "master_node_ip_address=10.154.2.91"
```
### 1.1 This command does the following:

ansible-playbook: Invokes Ansible to run a playbook. \
playbooks/create_primary_master_node.yml: Specifies the path to the playbook you want to execute.
-i inventories/production/hosts.ini: Sets the inventory file where Ansible will find the hosts to execute the playbook against. \
-e "node_name=tiger.loseyourip.com": Passes the node_name variable with the value tiger.loseyourip.com to the playbook. \
-e "master_node_ip_address=10.154.2.91": Passes the master_node_ip_address variable with the value 10.154.2.91 to the playbook.

## 2. Running these Playbooks from Semaphore
**Please refer to our readme.md file for more details on using Semaphore:** \
[Click this link to read this document](https://github.com/nic0michael/create-k3s-cluster-playbook-generator/tree/master/Semaphore)

## 3. The Node Servers for Cluster Deployment
```
Primary Master Node
tiger.loseyourip.com
10.154.2.91

Second Master Node
kudu.loseyourip.com
10.154.2.93 

Worker Node
leopard.loseyourip.com
10.154.2.95 	
  
Worker Node  
lion.loseyourip.com
10.154.2.97
```

**Please refer to our Inventory file for more details** \
[Click here to view Inventory File](https://github.com/nic0michael/create-k3s-cluster-playbook-generator/tree/master/inventories/production)
