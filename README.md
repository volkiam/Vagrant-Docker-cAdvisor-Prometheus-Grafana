Vagrant project for creatiing monitoring of dockers containers. Vagrant - Ansible - cAdvisor - Prometheus - Grafana

The Vagrant project, which creates an Ubuntu 20.04 VM, installs on it dockerand docker compose by using ansible. 
Next, docker compose creates 4 containers Grafana, Prometheus, cAdvisor, Redis:
Grafana - receives data from Prometheus and visualizes it on the dashboard.
Prometheus - receives data from cAdvisor.
cAdvisor - collects container metrics.
Redis - does nothing, just is.

Instruction to use (I used Ubuntu 20.04):

sudo apt update && sudo apt upgrade
sudo apt install virtualbox
curl -O https://releases.hashicorp.com/vagrant/2.2.19/vagrant_2.2.19_x86_64.deb
sudo apt install ./vagrant_2.2.19_x86_64.deb
mkdir ~/vagrant_project
cd ~/vagrant_project
#Download Vagrant box
wget https://app.vagrantup.com/generic/boxes/ubuntu2004/versions/4.1.8/providers/virtualbox.box 
#Append box to list
vagrant box add generic/ubuntu2004 virtualbox.box 
git clone https://github.com/volkiam/Vagrant-task1.git
vagrant up

After creating a virtual machine, grafana will be available at http://IP_address_of_VBox_VM:3000 or http://localhost:3000. For Login Use: admin:admin

If you want to connect to VM, please use "vagrant ssh" command.

For destroy VM, please use "vagrant destroy -f" command
