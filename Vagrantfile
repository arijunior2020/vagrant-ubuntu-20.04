Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "vagrant-ubuntu"
  config.vm.network "forwarded_port", guest: 80, host: 9090
  config.vm.network "public_network" , ip: "192.168.40.100"
  config.vm.provider "virtualbox" do |vb|
  vb.gui = true
  vb.memory = "1024"
  vb.cpus = "1"
  config.vm.provision "shell", path: "script.sh"
  config.vm.synced_folder "site/" , "/var/www/html"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
end
