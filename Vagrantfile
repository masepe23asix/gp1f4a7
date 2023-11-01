Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "gp1f4a7blue"
    vb.cpus = 2
    vb.memory = "2048"
  end

  config.vm.network "public_network", type: "dhcp"

  config.vm.hostname = "gp1f4a7blue.fjeclot.net"
  config.vm.define "gp1f4a7blue"

  config.vm.synced_folder "../codi", "/home/vagrant/gp1f4a7/codi"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y aptitude net-tools git zip unzip
    apt-get install -y docker.io
    usermod -aG docker vagrant
    sudo chown -R vagrant:vagrant /home/vagrant/gp1f4a7
  SHELL
end