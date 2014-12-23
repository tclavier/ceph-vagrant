# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "wheezy64"
  config.vm.box_url = "ftp://ftp.azae.net/vagrant/debian-wheezy-64.box"

  (1..3).each do |i|
    vm_name = "node#{i}"
    vm_ip = "192.168.33.#{i+10}"
    vm_fqdn = "#{vm_name}.ceph"

    config.vm.define vm_name do |hyp|
      hyp.vm.hostname = vm_fqdn
      hyp.vm.network :private_network, ip: vm_ip
      hyp.vm.provision 'shell', path: 'provision'
    end
  end
end

