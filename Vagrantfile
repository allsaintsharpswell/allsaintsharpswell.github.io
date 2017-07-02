# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 80, host: 8080 # nginx
  config.vm.provision :shell, :path => "provision.sh"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.customize ['guestproperty', 'set', :id, '/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold', 10000]
  end
end
