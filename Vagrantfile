# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "aqua-konosuba" do |py|
    py.vm.box = "centos/7"
    py.vm.box_url = "https://app.vagrantup.com/centos/boxes/7"
    py.vm.box_download_insecure = true
    py.vm.network "private_network", ip: "192.168.1.100"
    py.vm.hostname = "aqua-konosuba"

    py.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    py.vm.provision "shell", inline: <<-SHELL
      sudo yum update -y
      sudo yum install python3 -y
      sudo pip3 install requests qrcode pillow pyyaml
    SHELL
  end
end