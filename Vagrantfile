Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
 
  config.vm.provider "virtualbox" do |vb|
    vb.name = "test-vm-02"
    vb.memory = "2048"
    vb.cpus = 4
  end
  
  # forward grafana port
  config.vm.network "forwarded_port", guest: 3000, host: 3000

  # forward prometheus port
  config.vm.network "forwarded_port", guest: 9090, host: 9090  

  #forward cAdvisor port
  config.vm.network "forwarded_port", guest: 8080, host: 8080

#  config.vm.network "private_network", ip: "192.168.56.0"


# Provisioning configuration for Ansible.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./ansible/pb_install_docker.yml"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./ansible/pb_docker.yml"     
  end

end
