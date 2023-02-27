Vagrant.configure("2") do |config|
   config.vm.define :cliente do |cliente|
     cliente.vm.box = "centos/stream8"
     cliente.vm.network :private_network, ip: "192.168.50.2"
     cliente.vm.hostname = "cliente"
     cliente.vm.synced_folder ".", "/vagrant", type: "rsync"
     cliente.vm.provider "virtualbox" do |v|
        v.cpus = 2 
     end
   end
   config.vm.define :servidor do |servidor|
     servidor.vm.box = "centos/stream8"
     servidor.vm.network :private_network, ip: "192.168.50.3"
     servidor.vm.network "forwarded_port", host:5080, guest: 80
     servidor.vm.hostname = "servidor"
     servidor.vm.synced_folder ".", "/vagrant", type: "rsync"
     servidor.vm.provider "virtualbox" do |v|
        v.cpus = 2 
     end
   end
 end
