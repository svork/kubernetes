# Minimal Vagrant version: 2.2.4
Vagrant.require_version ">=2.2.4"

# Virtual machine name
VM_NAME = "kubemaster"
VM_NAME2 = "worker1"
VM_NAME3 = "worker2"

# Virtual machine private IP address
VM_PRIVATE_IP = "192.168.56.4"
VM_PRIVATE_IP2 = "192.168.56.5"
VM_PRIVATE_IP3 = "192.168.56.6"

# Box definition
Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"

  # VM1 - Kubernetes Master node
  config.vm.define "vm1" do |vm1|
    vm1.vm.network :private_network, ip: VM_PRIVATE_IP
    vm1.vm.hostname = VM_NAME

    # VM resources
    vm1.vm.provider :virtualbox do |vbox|
      vbox.name = VM_NAME
      vbox.cpus = 2
      vbox.memory= 2048 
    end

    # Ansible playbook details
    vm1.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "provisioning/site.yml"   
      ansible.inventory_path = "provisioning/hosts"
    end
  end

  # VM2 - Kubernetes Worker node 1
  config.vm.define "vm2" do |vm2|
    vm2.vm.network :private_network, ip: VM_PRIVATE_IP2
    vm2.vm.hostname = VM_NAME2

    # VM resources
    vm2.vm.provider :virtualbox do |vbox|
      vbox.name = VM_NAME2
      vbox.cpus = 2
      vbox.memory= 2048 
    end

    # Ansible playbook details
    vm2.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "provisioning/site.yml"   
      ansible.inventory_path = "provisioning/hosts"
    end
  end

  # VM3 - Kubernetes Worker node 2
  config.vm.define "vm3" do |vm3|
    vm3.vm.network :private_network, ip: VM_PRIVATE_IP3
    vm3.vm.hostname = VM_NAME3

    # VM resources
    vm3.vm.provider :virtualbox do |vbox|
      vbox.name = VM_NAME3
      vbox.cpus = 2
      vbox.memory= 2048 
    end

    # Ansible playbook details
    vm3.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "provisioning/site.yml"   
      ansible.inventory_path = "provisioning/hosts"
    end
  end
end
