# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "aqua-konosuba" do |py|
    py.vm.box = "centos/8"
    py.vm.box_url = "https://app.vagrantup.com/centos/boxes/8"
    py.vm.box_download_insecure = true
    py.vm.network "private_network", ip: "192.168.1.100"
    py.vm.hostname = "aqua-konosuba"

    py.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    py.vm.provision "shell", inline: <<-SHELL
      sudo dnf update -y
      sudo dnf install vim -y
      sudo dnf install python3 python3-devel -y
      sudo pip3 install requests qrcode pillow pyyaml
      sudo pip3 install ansible
      sudo pip3 install scrapy
      mkdir /home/vagrant/dev
      git clone https://github.com/nlog2n2/rice_cooker /home/vagrant/dev/rice_cooker
      git clone https://github.com/nlog2n2/chopping_board /home/vagrant/dev/chopping_board
      git config --global user.email "example@example.com"
      git config --global user.name "Toshihiro Sekiguchi"
    SHELL
  end
end