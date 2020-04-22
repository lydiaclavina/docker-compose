# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANT_API_VERSION="2"

DOCKER_IP	="192.168.33.106"

Vagrant.configure(VAGRANT_API_VERSION) do |config|

config.vm.define "docker" do |docker|
	docker.vm.box = "ubuntu/bionic64"
	docker.vm.hostname='docker'
  docker.vm.network :private_network, ip: DOCKER_IP
  docker.vm.network "forwarded_port", id: "tomcat", guest: 8080, host: 8080

	docker.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1024]
    end

	docker.vm.provision "shell", inline: <<-SCRIPT
        sudo apt-get update -y
        sudo apt-get remove docker docker-engine docker.io -y
        sudo apt install docker docker.io -y
        sudo apt install docker-compose -y

        groupadd docker
        usermod -aG docker vagrant
        sudo systemctl start docker
		SCRIPT
	end
end