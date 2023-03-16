Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/focal64'

  # Define vm1 and start the Swarm
  config.vm.define 'vm1' do |vm1|
    vm1.vm.hostname = 'vm1'
    vm1.vm.network 'private_network', ip: '192.168.50.11'
    vm1.vm.provision 'shell', inline: "docker swarm init --advertise-addr 192.168.50.11 | \
    grep 'docker swarm join' > /vagrant/swarm_join_command.sh"
  end

  # Define vm2 and join it to the Swarm
  config.vm.define 'vm2' do |vm2|
    vm2.vm.hostname = 'vm2'
    vm2.vm.network 'private_network', ip: '192.168.50.12'
    vm2.vm.provision 'shell', inline: 'bash /vagrant/swarm_join_command.sh'
  end

  # Define vm3 and join it to the Swarm
  config.vm.define 'vm3' do |vm3|
    vm3.vm.hostname = 'vm3'
    vm3.vm.network 'private_network', ip: '192.168.50.13'
    vm3.vm.provision 'shell', inline: 'bash /vagrant/swarm_join_command.sh'
  end
end
