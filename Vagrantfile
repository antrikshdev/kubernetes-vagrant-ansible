Vagrant.configure(2) do |config|

  # Kubernetes ansible Server
  config.vm.define "kubernetes-ansible" do |kansible|
    kansible.vm.box = "centos/7"
    kansible.vm.hostname = "kubernetes-ansible"
    kansible.vm.network "private_network", ip: "172.42.42.99"
    kansible.vm.provider "virtualbox" do |v|
      v.name = "kubernetes-ansible"
      v.memory = 1048
      v.cpus = 1
    end
  end
  # Kubernetes Master Server
  config.vm.define "kubernetes-master" do |kmaster|
    kmaster.vm.box = "centos/7"
    kmaster.vm.hostname = "kubernetes-master"
    kmaster.vm.network "private_network", ip: "172.42.42.100"
    kmaster.vm.provider "virtualbox" do |v|
      v.name = "kubernetes-master"
      v.memory = 1048
      v.cpus = 1
    end
  end

  NodeCount = 2

  # Kubernetes Worker Nodes
  (1..NodeCount).each do |i|
    config.vm.define "kubernetes-worker#{i}" do |workernode|
      workernode.vm.box = "centos/7"
      workernode.vm.hostname = "kubernetes-worker#{i}"
      workernode.vm.network "private_network", ip: "172.42.42.10#{i}"
      workernode.vm.provider "virtualbox" do |v|
        v.name = "kubernetes-worker#{i}"
        v.memory = 1024
        v.cpus = 1
      end
    end
  end

end
