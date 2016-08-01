# Vagrant file for launching manager node of Docker swarm.

Vagrant.configure("2") do |config|

  # https://atlas.hashicorp.com/ubuntu/boxes/xenial64
  ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

  config.vm.provision :shell, inline: <<EOS
apt-get update
apt-get install apt-transport-https ca-certificates
apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
echo 'deb https://apt.dockerproject.org/repo ubuntu-xenial main' >> /etc/apt/sources.list.d/docker.list

apt-get update
apt-get install -y docker-engine
EOS
  
  config.vm.define "manager1" do |manager|
    manager.vm.box = "ubuntu/xenial64"
    manager.vm.provider "virtualbox" do |v|
      v.name = "manager1"
    end
    manager.vm.hostname = "manager1"
    manager.vm.network "private_network", ip: "192.168.99.100"
  end

  config.vm.define "worker1" do |worker|
    worker.vm.box = "ubuntu/xenial64"
    worker.vm.provider "virtualbox" do |v|
      v.name = "worker1"
    end
    worker.vm.hostname = "worker1"
    worker.vm.network "private_network", ip: "192.168.99.101"
  end
  
  config.vm.define "worker2" do |worker|
    worker.vm.box = "ubuntu/xenial64"
    worker.vm.provider "virtualbox" do |v|
      v.name = "worker2"
    end
    worker.vm.hostname = "worker2"
    worker.vm.network "private_network", ip: "192.168.99.102"
  end

  
end
