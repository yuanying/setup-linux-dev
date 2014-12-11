# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "parallels/ubuntu-14.04"

  config.vm.network :private_network, ip: "192.168.43.96", parallels__name: "intnet"

  config.vm.provider "parallels" do |v|
    v.customize ["set", :id, "--nested-virt", "on"]
    v.memory  = 5120
    v.cpus    = 1
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "setup-vagrant.yml"
    ansible.host_key_checking = false
  end
end
