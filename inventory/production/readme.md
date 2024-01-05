## Creating the Inventory
run this command :
```
sudo nano /etc/ansible/hosts
```
Put this in the file:
```
# This is the default ansible 'hosts' file.

[primary_master_node]
hippo.kozow.com ansible_host=10.154.2.80

[other_active_nodes]
giraffe.kozow.com ansible_host=10.154.2.81
zebra.kozow.com ansible_host=10.154.2.83

[all_active_nodes]
hippo.kozow.com ansible_host=10.154.2.80
giraffe.kozow.com ansible_host=10.154.2.81
zebra.kozow.com ansible_host=10.154.2.83


[other_master_nodes]
giraffe.kozow.com ansible_host=10.154.2.81
#impala.kozow.com  ansible_host=10.154.2.82

[worker_nodes]
zebra.kozow.com ansible_host=10.154.2.83
#tiger.loseyourip.com ansible_host=10.154.2.91
#kudu.loseyourip.com ansible_host=10.154.2.93

[all_active_machines]
leopard.loseyourip.com ansible_host=10.154.2.95
upupa.loseyourip.com ansible_host=10.154.2.89
hippo.kozow.com ansible_host=10.154.2.80
giraffe.kozow.com ansible_host=10.154.2.81
zebra.kozow.com ansible_host=10.154.2.83

# Global variables
[all:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ansible
```
