# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
    config.vm.box = "planet"
    config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
    config.vm.box_download_insecure = true

    config.vm.network "private_network", ip: "192.168.60.10"
    config.vm.hostname = "planet.plone.org"

    config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: ".ssh/authorized_keys"

    config.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--ioapic", "on"  ]
        vb.customize ["modifyvm", :id, "--cpus"  , "2"   ]
        vb.customize ["modifyvm", :id, "--memory", "1024"]
        vb.customize ["modifyvm", :id, "--name", "planet" ]
    end

 end
