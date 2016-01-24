# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'yaml'

vars = YAML.load_file('vars.yml')

Vagrant.configure(2) do |config|
  config.vm.box = "debian/jessie64"
  config.vm.hostname = "devstack"
  config.vm.network :private_network, ip: vars["vagrant_host"]
  config.vm.provider :virtualbox do |vb|
    vb.memory = 1024
    vb.cpus = 2
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "run.yml"
  end
end
