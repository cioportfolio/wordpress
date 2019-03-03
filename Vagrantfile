# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/xenial64"
#  config.vm.network :private_network, ip: "192.168.99.99"
  config.vm.provision :shell, :path => "bootstrap.sh"
  config.vm.provision :shell, :path => "startup.sh", run: "always"
  config.vm.synced_folder ".", "/var/www"
  config.vm.network "forwarded_port", guest: 8080, host: 8080, host_ip: "127.0.0.1"
end