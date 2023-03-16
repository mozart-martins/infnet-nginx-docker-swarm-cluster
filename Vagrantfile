Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/focal64'
  config.vm.define 'vm1' do |vm1|
    vm1.vm.hostname = 'vm1'
    vm1.vm.network 'private_network', ip: '192.168.50.11'
  end
  config.vm.define 'vm2' do |vm2|
    vm2.vm.hostname = 'vm2'
    vm2.vm.network 'private_network', ip: '192.168.50.12'
  end
  config.vm.define 'vm3' do |vm3|
    vm3.vm.hostname = 'vm3'
    vm3.vm.network 'private_network', ip: '192.168.50.13'
  end
  config.vm.provision 'docker'
end
