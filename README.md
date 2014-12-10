# VagrantIcecream: An Icecream client machine, set up with Vagrant

VagrantIcecream is a Vagrant configuration to create a VM that runs
iceccd's daemon. It offers a simple solution to integrate for example
Windows and OSX machines into the Icecream network.

## Usage

Assuming Vagrant is already installed on the host machine, all it
takes to create a VM that runs _iceccd_ is to clone this repository
and to run `vagrant up` in it. Since _iceccd_ clients register with the
scheduler automatically, no further configuration is needed.

## How it works

Initializing VagrantIcecream with `vagrant up` will create a temporary
VM in the _.vagrant_ folder in the repository. Puppet will then be
used to install the _icecc_ package. The box will simply use the
default setup of _icecc_, running the daemon but not the
scheduler. The box will use bridged networking to expose the _icecc_
client on the network.

When the machine is not needed anymore, get rid of it by running
`vagrant destroy`.

