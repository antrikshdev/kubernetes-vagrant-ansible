# Kubernetes Cluster using Ansible
* Clone repository.
* Create multiple centos7 servers. One Anisble controller, One master and 2 worker nodes. Use vagrant file to provisioning the 4 VM's in oracle virtual box.
* Use the following command 
  1. vagrant box add centos/7
  2. vagrant up 
* cd kubernetes-vagrant-ansible/centos/playbooks/
* Change the “ad_addr” in the env_variables file with the IP address of the Kubernetes master node.
* Add the IP Addresses of the worker nodes and the master node in the “hosts” file.
* Run the following command to setup the Kubernetes Master node.

```
ansible-playbook setup_master_node.yml
```
* Once the master node is ready, run the following command to set up the worker nodes.

```
ansible-playbook setup_worker_nodes.yml
```

* Once the workers have joined the cluster, run the following command to check the status of the worker nodes.
```
kubectl get nodes
```




