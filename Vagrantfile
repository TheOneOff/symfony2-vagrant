# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "puppetlabs/ubuntu-14.04-64-puppet"
    config.vm.network "private_network", ip: "33.33.33.100"
    config.vm.synced_folder ".", "/vagrant",
    	:nfs => (RUBY_PLATFORM =~ /linux/ or RUBY_PLATFORM =~ /darwin/)

    config.vm.provision :puppet do |puppet|
        puppet.manifests_path = "puppet/manifests"
        puppet.module_path = "puppet/modules"
        puppet.options = ['--verbose']
    end

    config.vm.provider "virtualbox" do |v|
      v.memory = 4096
    end
end