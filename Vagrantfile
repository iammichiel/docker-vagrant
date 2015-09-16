# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # Basic settings
    config.vm.box = "ubuntu/trusty64"
    config.vm.box_check_update = false

    # Network settings
    config.ssh.forward_x11 = true
    config.vm.network "private_network", ip: "192.168.5.10"

    # Shared folder
    config.vm.synced_folder ".", "/vagrant", :nfs => true

    # Hardware settings
    config.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.customize ["modifyvm", :id, "--memory", "2048"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    end

    # Setup box
    config.vm.provision :shell, path: "bin/vagrant"
end
