# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_NO_PARALLEL'] = 'yes'

Vagrant.configure(2) do |config|

  #config.vm.provision "shell", path: "bootstrap.sh"

  # Kubernetes Master Server
  config.vm.define "jenkins-test-vm" do |kmaster|
    kmaster.vm.box = "centos/7"
    kmaster.vm.hostname = "jenkins-test-vm"
    kmaster.vm.network "private_network", ip: "172.50.50.100"
    kmaster.vm.provider "virtualbox" do |v|
      v.name = "jenkins-test-vm"
      v.memory = 2048
      v.cpus = 2
      # Prevent VirtualBox from interfering with host audio stack
      v.customize ["modifyvm", :id, "--audio", "none"]
    end
    #kmaster.vm.provision "shell", path: "bootstrap_kmaster.sh"
  end
end
