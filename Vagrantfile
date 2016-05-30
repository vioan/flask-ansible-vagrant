# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
VAGRANT_IP = "192.168.0.60"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "opensuse/openSUSE-13.2-x86_64"
  config.vm.network "private_network", ip: VAGRANT_IP
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 5000, host: 8050

  config.vm.synced_folder "app/", "/home/userapp/app", create: true

   config.vm.provider "virtualbox" do |vb|
     vb.gui = false
     vb.name = "flask"
     vb.memory = "1024"
   end

   config.vm.provision "ansible" do |ansible|
     ansible.playbook = "ansible/playbook.yml"
     ansible.inventory_path = "ansible/hosts"
     ansible.limit = "all"
   end
end
