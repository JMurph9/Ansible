# -*- mode: ruby -*-
# vi: set ft=ruby :
#11-12

Vagrant.configure(2) do |config|
	 config.vm.box = "chad-thompson/ubuntu-trusty64-gui"
	 config.vm.synced_folder "shared", "/tmp/shared"
	 
	 config.vm.provider "virtualbox" do |vb|
	 vb.gui = true
	 vb.memory = 4096
	 vb.cpus=2
	 end
	 
	 config.vm.define "ansiMasterJM" do |masterJM|
		masterJM.vm.hostname = "masterJM.qac.local"
		masterJM.vm.network :public_network, ip: "192.168.1.111"
		masterJM.vm.provision "shell", path: "masterBootstrap.sh"
	end 
	
	config.vm.define "ansiAgentJM" do |agentJM|
		agentJM.vm.hostname = "masterJM.qac.local"
		agentJM.vm.network :public_network, ip: "192.168.1.112"
		agentJM.vm.provision :shell, path: "agentBootstrap.sh"
	end 
end
