# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/xenial64'

  config.vm.network 'forwarded_port', guest: 80, host: 8080
  config.vm.network 'private_network', ip: '192.168.50.12'

  config.vm.synced_folder '.', '/home/vagrant/tiny-web-server', type: :nfs

  config.vm.provider 'virtualbox' do |vb|
    vb.gui = false
    vb.cpus = 1
    vb.memory = 1024
  end

  config.vm.provision :shell, inline: <<-SHELL
    sudo apt-get install -y gcc
  SHELL
end
