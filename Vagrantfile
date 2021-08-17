Vagrant.configure("2") do |config| 
  # box
  config.vm.box = "rbock44/ubuntu20.04"
  config.vm.box_version = "1.0.0"
  # IP
  config.vm.network "private_network", ip: "192.168.33.26"
  # メモリ/CPU
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 16384
    vb.cpus = 6
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.become = true
    ansible.playbook = "playbook.yml"
  end
end
