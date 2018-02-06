# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box_check_update = false

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = 512
  end

  # WEB hosts
  config.vm.define 'precise-web' do |precise|
    precise.vm.box = "ubuntu/precise64"
    precise.vm.network "private_network", ip: "192.168.33.10"  
  end

  config.vm.define 'trusty-web' do |trusty|
    trusty.vm.box = "ubuntu/trusty64"
    trusty.vm.network "private_network", ip: "192.168.33.11"  
  end

  config.vm.define 'xenial-web' do |xenial|
    xenial.vm.box = "ubuntu/xenial64"
    xenial.vm.network "private_network", ip: "192.168.33.12"  
  end

  config.vm.define 'centos7-web' do |centos7|
    centos7.vm.box = "centos/7"
    centos7.vm.network "private_network", ip: "192.168.33.13"  
  end

  # DB hosts
  config.vm.define 'precise-db' do |precise|
    precise.vm.box = "ubuntu/precise64"
    precise.vm.network "private_network", ip: "192.168.33.14"  
  end

  config.vm.define 'trusty-db' do |trusty|
    trusty.vm.box = "ubuntu/trusty64"
    trusty.vm.network "private_network", ip: "192.168.33.15"  
  end

  config.vm.define 'xenial-db' do |xenial|
    xenial.vm.box = "ubuntu/xenial64"
    xenial.vm.network "private_network", ip: "192.168.33.16"  
  end

  config.vm.define 'centos7-db' do |centos7|
    centos7.vm.box = "centos/7"
    centos7.vm.network "private_network", ip: "192.168.33.17"  
  end
end
