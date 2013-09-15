Vagrant.configure("2") do |config|
  config.vm.box = "obsd-current-i386"

  config.vm.network :private_network, ip: "192.168.50.4"

  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--memory", 512]
    v.customize ["modifyvm", :id, "--name", "obsd-porter-current-i386"]
  end

  ## For masterless, mount your file roots file root
  #config.vm.synced_folder "salt/roots/", "/srv/"
  #config.vm.synced_folder "./openbsd-wip", "/usr/ports/openbsd-wip", nfs: true
  # THIS WORKS:
  config.vm.synced_folder "./vagrant", "/vagrant", id: "root", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/distfiles", "/usr/ports/distfiles", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/packages/current", "/usr/ports/packages", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/openbsd-wip", "/usr/ports/openbsd-wip", :nfs => true

  ## Set your salt configs here
  #config.vm.provision :salt do |salt|

    ## Minion config is set to ``file_client: local`` for masterless
    #salt.minion_config = "salt/minion"

    ## Installs our example formula in "salt/roots/salt"
    #salt.run_highstate = true

  #end
end
