# Minimal Vagrant version: 2.2.4
Vagrant.require_version ">=2.2.4"

# Box definition
Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"

  # VM1 - Kubernetes Master node
  config.vm.define "kubemaster" do |kubemaster|
    kubemaster.vm.network :private_network, ip: "192.168.56.4"
    kubemaster.vm.hostname = "kubemaster"

    # VM resources
    kubemaster.vm.provider :virtualbox do |vbox|
      vbox.name = "kubemaster"
      vbox.cpus = 2
      vbox.memory= 2048 
    end

    # Ansible playbook details
    kubemaster.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "provisioning/site.yml"   
      ansible.inventory_path = "provisioning/hosts"
    end
  end

  # VM2 - Kubernetes Worker node 1
  config.vm.define "worker1" do |worker1|
    worker1.vm.network :private_network, ip: "192.168.56.5"
    worker1.vm.hostname = "worker1"

    # VM resources
    worker1.vm.provider :virtualbox do |vbox|
      vbox.name = "worker1"
      vbox.cpus = 2
      vbox.memory= 2048 
    end

    # Ansible playbook details
    worker1.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "provisioning/site.yml"   
      ansible.inventory_path = "provisioning/hosts"
    end
  end

  # VM3 - Kubernetes Worker node 2
  config.vm.define "worker2" do |worker2|
    worker2.vm.network :private_network, ip: "192.168.56.6"
    worker2.vm.hostname = "worker2"

    # VM resources
    worker2.vm.provider :virtualbox do |vbox|
      vbox.name = "worker2"
      vbox.cpus = 2
      vbox.memory= 2048 
    end

    # Ansible playbook details
    worker2.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "provisioning/site.yml"   
      ansible.inventory_path = "provisioning/hosts"
    end
  end
end
