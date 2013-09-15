vagrant-obsd-port-worker
========================

Vagrant setup for working on OpenBSD ports

Currently set up only for i386, soon I will modify it to set up both i386
and amd64 boxes.

Currently mounts inside the machine via NFS:
  config.vm.synced_folder "./vagrant", "/vagrant", id: "root", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/distfiles", "/usr/ports/distfiles", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/packages/current", "/usr/ports/packages", :nfs => true
  config.vm.synced_folder "~/Work/OpenBSD/openbsd-wip", "/usr/ports/openbsd-wip", :nfs => true

