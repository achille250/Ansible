# Vagrantfile
Vagrant.configure("2") do |config|
  config.vm.define "web_server" do |web|
  web.vm.box = "debian/bullseye64"
  web.vm.network "private_network", ip: "192.168.33.10"
  web.vm.hostname="web-server"

  web.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end
  
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y python3 python3-pip
    pip3 install ansible
  SHELL
end
end
