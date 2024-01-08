Please note The creation of the Primary Master Node is a manual process \
You need to run the following commands first on the Primary Master Node Server:
```
sudo su -
cd /opt/k3s
./primary_master_node.sh
```

After the K3S Primary master Node is created you need to run the following commands:
```
# Check that the Kubernetes Cluster was created
kubectl get Nodes

# Get the Kubernetes Cluster Security Token
cat /var/lib/rancher/k3s/server/node-token
```
Now use this Kubernetes Cluster Security Token to edit the following files in your Ansible Project:
```
vars/other_master_node_variables.yml

and

vars/worker_node_variables.yml
```

Now run the following Playbooks:
```
playbooks/run_k3s_scripts/start_other_master_node_in_k3s_cluster.yml

and

playbooks/run_k3s_scripts/start_worker_node_in_k3s_cluster.yml
```
