# -*- mode: ruby -*-
VAGRANTFILE_API_VERSION = "2"
#
# A Vagrant configuration that creates a VM that runs iceccd's
# daemon. It offers a simple solution to integrate for example Windows
# and OSX machines into the Icecream network:

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "phusion/ubuntu-14.04-amd64"
  # Bridged network is needed for icecc to find it's scheduler:
  config.vm.network "public_network"

  config.vm.provision :shell, :inline => 'apt-get install --yes puppet'

  config.vm.provision "puppet" do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file  = "icecream.pp"
  end

end
