# -*- mode: ruby -*-
# vi: set ft=ruby :
require './parameters.rb'
include MyVars

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "sf" do |sf_config|
    sf_config.vm.box = "wheezy64"
    sf_config.vm.box_url = "http://downloads.shadoware.org/wheezy64.box"
    sf_config.vm.hostname = 'machine1'
    sf_config.vm.network :"private_network", ip: "192.168.40.10"
    sf_config.vm.synced_folder PATH_SHARE_FOLDER, PATH_MOUNT_FOLDER, :nfs => true

    config.vm.provider :virtualbox do |v|
      v.name = SF_VM_NAME
    end

    sf_config.vm.provision :ansible do |ansible|
      ansible.inventory_path = "devops/hosts"
      ansible.playbook = "devops/site.yml"
      ansible.verbose = ANSIBLE_VERBOSE
      ansible.limit = 'all'
    end
  end
end
