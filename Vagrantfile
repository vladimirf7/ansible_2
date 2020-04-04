# -*- mode: ruby -*-
# vi: set ft=ruby :

# Run with: vagrant up --provider hyperv

Vagrant.configure("2") do |config|
    config.vm.box = "generic/ubuntu1804"
    config.vm.network "public_network"
    config.vm.provider "hyperv" do |h|
      h.memory = 512
    end
    config.vm.provision "shell", privileged: false, inline: <<-SHELL
      sudo apt-add-repository --yes --update ppa:ansible/ansible
      sudo apt-get install software-properties-common ansible git sshpass python-pip -y
      pip install pywinrm
      git clone https://github.com/vladimirf7/ansible_2.git
    SHELL
  end
