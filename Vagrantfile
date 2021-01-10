# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do | config |
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://app.vagrantup.com/ubuntu/boxes/trusty64"
  config.vm.box_download_insecure = true

  config.vm.define :server1 do | server1 |
    server1.vm.network "private_network", ip: "192.168.1.100"
    server1.vm.network "private_network", ip: "192.168.2.100"
    server1.vm.network "forwarded_port", guest: 22 , host: 2222
    server1.vm.hostname = "megumin-konosuba"

    server1.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = "1"
    end
  end

  config.vm.define :server2 do | server2 |
    server2.vm.network "private_network", ip: "192.168.1.101"
    server2.vm.network "private_network", ip: "192.168.2.101"
    server2.vm.network "forwarded_port", guest: 22 , host: 3322
    server2.vm.hostname = "darkness-konosuba"

    server2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = "1"
    end
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update && apt-get dist-upgrade
    sudo apt-get install ansible
  SHELL

end
