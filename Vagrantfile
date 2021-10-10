# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
   config.vm.network "forwarded_port", guest: 3000, host: 3000

   config.vm.synced_folder "./data", "/vagrant_data", type: "rsync"
   config.vm.provider "libvirt" do |domain|
	domain.driver = "kvm"
	domain.host = 'localhost'
	domain.uri = 'qemu:///system'
	domain.memory = 1024
	domain.cpus = 1
   end

  config.vm.provision "ansible" do |ansible|
   ansible.verbose = "v"
   ansible.playbook = "playbook.yml"
  end

end
