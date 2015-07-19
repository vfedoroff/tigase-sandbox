# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.provider "virtualbox" do |v, override|
    v.customize ["modifyvm", :id, "--memory", 1024]
    v.customize ["modifyvm", :id, "--cpus", 2]
    override.vm.network :private_network, ip: "192.168.33.10"
    override.vm.box = "ubuntu/trusty64"
  end

  config.vm.hostname="tigase.example.com"

  config.vm.provision "shell" do |sh|
        sh.path = "ansible.sh"
        sh.args = "ansible/playbook.yml ansible/inventory"
  end
end
