Vagrant.configure("2") do |config|
  config.vm.provision "shell", path: "bootstrap.sh"

#server1
  config.vm.define "web" do |web|
    web.vm.box = "centos/8"
    web.vm.hostname = "server1"
    web.vm.box_version = "1905.1"
    web.vm.provider :virtualbox
    web.vm.disk :disk, size: "100GB", primary: true

    web.vm.network "private_network", ip: "192.168.56.4",        
        name: "vboxnet0"
    web.vm.provider "virtualbox" do |v|
	v.name = "server1"
        v.memory = 1024
  	v.cpus = 2
	end 
  end

#server2
  config.vm.define "web1" do |web1|
    web1.vm.box = "centos/8"
    web1.vm.hostname = "server2"
    web1.vm.box_version = "1905.1"
    web1.vm.network "private_network", ip: "192.168.56.5",
        name: "vboxnet0"
    web1.vm.provider "virtualbox" do |v|
        v.name = "server2"
        v.memory = 1024
        v.cpus = 2
        end
  end



end

