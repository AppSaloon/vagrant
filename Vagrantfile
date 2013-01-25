Vagrant::Config.run do |config|
  config.vm.box = "asdev"

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  config.vm.forward_port 80, 80
  config.vm.forward_port 3306, 3306

  config.vm.network :hostonly, "33.33.33.10"
  config.vm.host_name = "vagrant.local"

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "server/manifests"
    puppet.manifest_file  = "base.pp"
    puppet.module_path = "server/modules"
    #puppet.options = "--verbose --debug"
    #puppet.options = "--verbose"
  end
end

