# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "peru/ubuntu-20.04-desktop-amd64"
  config.vm.box_version = "20200707.01"

  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 8081, host: 8081

  config.vm.provider "virtualbox" do |vb|
    vb.name = "Ubuntu_Desktop_20.04"
    vb.memory = "4096"
    vb.cpus = 4
  end
  # This is for the playbooks
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.install_mode = "pip"
  end

end