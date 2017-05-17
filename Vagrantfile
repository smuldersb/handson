# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

 config.vm.define "cd" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "cd"
    m.vm.network "private_network", ip: "10.0.10.101"
    m.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
  end

  config.vm.define "collaboration" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "collaboration"
    m.vm.network "private_network", ip: "10.0.10.102"
    m.vm.provider "virtualbox" do |v|
      v.memory = 1024
    end
  end

  config.vm.define "test" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "test"
    m.vm.network "private_network", ip: "10.0.11.100"
    m.vm.provider "virtualbox" do |v|
      v.memory = 1024
    end
  end

  config.vm.define "prod" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "prod-proxy"
    m.vm.network "private_network", ip: "10.0.13.100"
    m.vm.provider "virtualbox" do |v|
      v.memory = 1024
    end
  end

  config.vm.define "control" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "control"
    m.vm.network "private_network", ip: "10.0.10.100"
    m.vm.provision :shell, path: "scripts/bootstrap_ansible.sh"
    m.vm.provision :shell, inline: "ansible-playbook /vagrant/ansible/playbook.yml -i /vagrant/ansible/hosts/hosts.yml"
    m.vm.provider "virtualbox" do |v|
      v.memory = 1024
    end
  end

end
