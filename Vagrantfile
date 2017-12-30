# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box_check_update = true

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = 512
  end

  config.vm.provision "bootstrap", type: "shell" do |s|
    s.inline = "echo 'bootstrap provisioner'"
    s.inline = "sudo service networking restart || sudo service network restart"
  end

  config.vm.define 'xenial' do |xenial|
    xenial.vm.box = "ubuntu/xenial64"
    xenial.vm.network "private_network", ip: "192.168.33.10"  
  end

  config.vm.define 'centos7' do |centos7|
  centos7.vm.box = "centos/7"
    centos7.vm.network "private_network", ip: "192.168.33.11"  
  end
end
