Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 9100, host: 9100
  config.vm.network "forwarded_port", guest: 9090, host: 9090
  config.vm.boot_timeout = 600
  config.vm.provider "virtualbox" do |hv|
    hv.name = "ubuntu_ansible_roles"
    hv.memory = "2048"
    hv.cpus = 2
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "install_all.yml"
  end
end