# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end
 
  config.vm.define "docker" do |docker|
    docker.vm.network "private_network", ip: "192.168.1.10", virtualbox__intnet: "local"
    docker.vm.hostname = "docker"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.become = "true"
  end

end
