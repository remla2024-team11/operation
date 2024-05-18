Vagrant.configure("2") do |config|
  # Define the number of worker nodes
  N = 2

  # Define base box
  config.vm.box = "bento/ubuntu-24.04"
  config.vm.box_version = "202404.26.0"
  
  config.vm.provider "vmware_desktop" do |v|
    v.gui = true
  end

  # Define the controller node
  config.vm.define "controller" do |controller|
    controller.vm.network "private_network", type: "dhcp"
    controller.vm.provider "virtualbox" do |vb|
      vb.memory = 4096
      vb.cpus = 1
    end
  end

  # Define worker nodes
  (1..N).each do |i|
    config.vm.define "node#{i}" do |node|
      node.vm.network "private_network", type: "dhcp"
      node.vm.provider "virtualbox" do |vb|
        vb.memory = 6144
        vb.cpus = 2
      end
    end
  end

  # Provision the VMs with Ansible
  config.vm.provision :ansible do |a|
    a.compatibility_mode = "2.0"
    a.playbook = "provisioning.yml"
    a.verbose = "vvv"
  end
end