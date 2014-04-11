# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :i386 do |i386|
    i386.vm.box = "obsd-current-i386"
    i386.vm.network :private_network, ip: "192.168.50.4", type: "static"
  end

  config.vm.define :amd64 do |amd64|
    amd64.vm.box = "obsd-current-amd64"
    amd64.vm.network :private_network, ip: "192.168.50.5", type: "static"
  end

  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--memory", 512]
  end

  ## For masterless, mount your file roots file root
  #config.vm.synced_folder "salt/roots/", "/srv/"
  #config.vm.synced_folder "./openbsd-wip", "/usr/ports/openbsd-wip", nfs: true
  # THIS WORKS:
  config.vm.synced_folder "./vagrant", "/vagrant", id: "root", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/distfiles", "/usr/ports/distfiles", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/packages/current", "/usr/ports/packages", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/openbsd-wip", "/usr/ports/openbsd-wip", :nfs => true
end
