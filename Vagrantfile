VAGRANTFILE_API_VERSION = "2"
 Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos/8"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "maria.yml"
    ansible.become = true
  end
  config.vm.define "primary" do |primary|
    primary.vm.hostname = "primary"
    primary.vm.network "forwarded_port", guest: 3306, host: 3336
    primary.vm.network "private_network", ip: "192.168.40.2"
  end
  config.vm.define "secondary" do |secondary|
    secondary.vm.hostname = "secondary"
    secondary.vm.network "forwarded_port", guest: 3306, host: 3337
    secondary.vm.network "private_network", ip: "192.168.40.3"
  end
  config.vm.provider "virtualbox" do |box|
    box.memory = 1024
    box.cpus = 2
  end
end
