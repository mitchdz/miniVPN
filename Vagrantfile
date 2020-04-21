# -*- mode: ruby -*-
# vi: set ft=ruby :

#BOX_IMAGE = "ubuntu/trusty64"
BOX_IMAGE = "ediaz/SEEDUbuntu-16.04-32bit"
BOX_VERSION = "0.0.1"

Vagrant.configure(2) do |config|
    config.vm.define "client" do |client|    
        client.vm.hostname = "client"
        client.vm.box = BOX_IMAGE
        client.vm.box_version = BOX_VERSION
        client.vm.network "private_network", ip: "10.0.2.7"
    end
    config.vm.define "server" do |server|    
        server.vm.hostname = "server"
        server.vm.box = BOX_IMAGE
        server.vm.box_version = BOX_VERSION
        server.vm.network "private_network", ip: "10.0.2.8"
    end
    config.vm.define "target" do |target|    
        target.vm.hostname = "target"
        target.vm.box = BOX_IMAGE
        target.vm.box_version = BOX_VERSION
        target.vm.network "private_network", ip: "192.168.60.101"
    end
end
