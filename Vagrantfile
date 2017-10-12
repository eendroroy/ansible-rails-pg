# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "centos/7"
  config.vm.box_check_update = true
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = 2048
  end

  config.vm.provision "bootstrap", type: "shell" do |s|
    s.inline = "echo 'bootstrap provisioner'"
    s.inline = "sudo /etc/init.d/network restart"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.limit = "all"
    ansible.inventory_path = "./hosts"
    ansible.playbook = "./vagrant.yml"
  end
end
