# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.box = "debian/jessie64"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 80, host: 8888

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.33.10", virtualbox__intnet: "vboxnet0"
  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"
 
 config.vm.provider "virtualbox" do |vb|
     vb.gui = true
     vb.memory = "4096"
#     vb.customize [
#            'createhd', 
#            '--format', 'VDI', 
#            '--filename', '/media/julien/c28c9c83-3d4b-42e7-bb18-92ca49adbebe/osm/modtile.vdi', 
#            '--size', 200*1024*1024 # 50 GB
#            ] 
   end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "osmtile.yml"
  end
end
