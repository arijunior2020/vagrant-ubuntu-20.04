Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "vagrant-ubuntu"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "public_network"
  config.vm.provider "virtualbox" do |vb|
  vb.gui = true
  vb.memory = "1024"
  config.vm.provision "shell", inline: <<-SHELL
  apt-get update
  apt-get install -y nginx
  SHELL
end
end

