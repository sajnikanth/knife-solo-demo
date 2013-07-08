# -*- mode: ruby -*-
# vi: set ft=ruby :
# encoding: utf-8

Vagrant.configure("2") do |config|
  config.vm.box = "base"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/raring/current/raring-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.network :private_network, ip: "192.168.12.34"
  config.vm.provider :virtualbox do |vb|
    vb.name = "ubuntu"
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
  config.omnibus.chef_version = :latest
end
