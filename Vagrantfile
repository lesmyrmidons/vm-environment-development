# -*- mode: ruby -*-
# vi: set ft=ruby :
require './paramters.rb'
include MyVars

Vagrant::Config.run do |config|
  config.vm.define :sf do |sf_config|
    sf_config.vm.box = "wheezy64"
    sf_config.vm.hostname = SFVMNAME
    sf_config.vm.box_url = "http://downloads.shadoware.org/wheezy64.box"
    sf_config.vm.network :hostonly, "192.168.40.10"
    sf_config.vm.share_folder("v-root", "/vagrant", PATHSHAREFOLDER, :nfs => true)

    sf_config.vm.provision "ansible" do |ansible|
      ansible.inventory_path = "devops/hosts"
      ansible.playbook = "devops/site.yml"
      ansible.inventory_path = "develops/hosts"
      ansible.hosts = "sfserver"
      ansible.verbose = "-vvv"
    end
  end
end
