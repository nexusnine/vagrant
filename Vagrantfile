# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.define :puppet2 do |puppet2_config|
  puppet2_config.vm.box       = "centos-6.4-x86_64"
  puppet2_config.vm.box_url   = "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20130309.box"
  puppet2_config.vm.host_name = "development.puppetlabs.vm"
  puppet2_config.vm.network :hostonly, "192.168.33.10"
  puppet2_config.vm.forward_port 80, 8084
  puppet2_config.vm.provision :shell, :path => "centos_6_x.sh"
# Puppet Shared Folder
  puppet2_config.vm.share_folder "puppet_mount", "/puppet", "puppet"
  # Puppet Provisioner setup
  puppet2_config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path    = "puppet/modules"
    puppet.manifest_file  = "site.pp"
end
  config.vm.define :master do |master_config|
    master_config.vm.box = "centos-56-x64"
    master_config.vm.network :bridged
#    master_config.vm.base_mac = "08:00:27:b5:75:6c"
  end
  config.vm.define :web1 do |web1_config|
    web1_config.vm.box = "centos-56-x64"
    web1_config.vm.network :bridged
#    web1_config.vm.base_mac = "08:00:27:b5:75:6d"
  end
  config.vm.define :fms1 do |fms1_config|
    fms1_config.vm.box = "centos-56-x64"
    fms1_config.vm.network :bridged
#    fms1_config.vm.base_mac = "08:00:27:b5:75:6d"
  end
  config.vm.define :log1 do |log1_config|
    log1_config.vm.box = "centos-server-63-x64"
    log1_config.vm.network :bridged
  end
  config.vm.define :puppet1 do |puppet1_config|
    puppet1_config.vm.box = "centos-6.4-x64"
    puppet1_config.vm.network :bridged
  end
#Vagrant::Config.run do |config|
#  config.vm.box       = "centos-6.3-x86_64"
#  config.vm.box_url   = "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20130309.box"
#  config.vm.host_name = "development.puppetlabs.vm"
#  config.vm.network :hostonly, "192.168.33.10"
#  config.vm.forward_port 80, 8084
#  config.vm.provision :shell, :path => "centos_6_x.sh"
end
end
