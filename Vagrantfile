# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Use default 32-bit Ubuntu VM
  config.vm.box = "hashicorp/precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"

  # Provisioning
  config.vm.provision :shell, path: "bootstrap.sh"

  config.vm.synced_folder "krig-game-engine/", "/home/vagrant/krig-game-engine/"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # VirtualBox:
  config.vm.provider :virtualbox do |vb|
   vb.gui = true
   vb.customize ["modifyvm", :id, "--memory", "2048"]
   vb.customize ["modifyvm", :id, "--vram", "128"]
   vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
  end
end
