# -*- mode: ruby -*-
# vi: set ft=ruby :


#Sample Vagrant config

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "SampleVM"
  config.vm.provision "shell", path: "bootstrap.sh"

  #hostmanager
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true
  config.vm.define 'SampleVM' do |node|
    node.vm.hostname = 'sample.url'
    node.vm.network :private_network, ip: '192.168.42.42'
    node.hostmanager.aliases = %w(www.sample.url)
  end

  #Sync Folder : https://www.vagrantup.com/docs/synced-folders/
  config.vm.synced_folder "/path/to/my/local/folder", "/path/to/my/vm/folder"

end
