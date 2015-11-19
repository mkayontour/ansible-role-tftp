# vi: set ft=ruby

require 'rbconfig'

ROLE_NAME = 'tftp'
HOST_NAME = 'test' + ROLE_NAME
VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = 'bertvv/centos71'
  config.vm.define HOST_NAME do |node|
    node.vm.network "forwarded_port",  guest: 69, host: 6969, protocol: 'udp'
    node.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'test.yml'
    end
  end
end

