
Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 32066, host: 32066

  config.vm.network "private_network", ip: "192.168.90.20"

  config.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 2
  end

  config.vm.define "prueba" do |prueba|
    prueba.vm.provision "ansible" do |ansible|
      ansible.verbose = 'vvv'
      ansible.playbook = "ansible/infraestructure.yml"
    end
  end
end
