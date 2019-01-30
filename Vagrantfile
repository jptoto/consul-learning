# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/bionic64"
  config.vm.provision 'shell', path: 'install_consul.sh'
  
  # Servers
  1.upto(1) do |i|
    vm_name = "consul-instance-#{i}"
    vm_ip = "192.68.50.1#{i}"
    config.vm.define vm_name do |server|
      server.vm.hostname = vm_name
      server.vm.network 'private_network', ip: vm_ip
    end
  end
end
