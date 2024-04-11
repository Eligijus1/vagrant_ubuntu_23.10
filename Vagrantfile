# Require vagrant 1.8 or newer:
Vagrant.require_version ">= 1.8"

# BOX Configuration:
Vagrant.configure("2") do |config|
    # Configure our project to use ubuntu 23.10 Vagrant Box (https://app.vagrantup.com/generic/boxes/ubuntu2310):
    config.vm.box = "generic/ubuntu2310"

    # The hostname the machine should have:
    config.vm.hostname = "vagrant.test"

    # Configures networks on the machine:
    config.vm.network "private_network", ip: "172.28.128.30"

    # Configure machine settings:
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
    end

    # Enable additional provisioning with a shell script:
    config.vm.provision "shell", inline: <<-SHELL
        echo "# IPv4 and IPv6 localhost aliases:" | sudo tee /etc/hosts
        echo "127.0.0.1 vagrant.testt vagrant.test localhost" | sudo tee -a /etc/hosts
        echo "::1       vagrant.test  vagrant.test localhost" | sudo tee -a /etc/hosts
        sudo apt-get update
		sudo apt-get install -y nmap	
		echo "nameserver 8.8.8.8" | sudo tee -a /etc/resolv.conf
        echo "nameserver 8.8.4.4" | sudo tee -a /etc/resolv.conf
		sudo apt-get install -y git
		sudo apt-get install -y zip unzip
        sudo apt install -y net-tools
		sudo apt-get install jq -y
		sudo apt-get install jq -y

	    echo "+-------------------------------------+"
	    echo "|                                     |"
	    echo "|      Installed utils                |"
	    echo "|                                     |"
	    echo "+-------------------------------------+"

		#sudo apt-get update
        #sudo apt-get install -y ca-certificates curl
        #sudo install -m 0755 -d /etc/apt/keyrings
        #sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
        #sudo chmod a+r /etc/apt/keyrings/docker.asc
        #echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
        #sudo apt-get update
		#sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
		#docker run hello-world
		#sudo apt-get install docker-compose -y
        #docker-compose -v
		#sudo groupadd docker
        #sudo usermod -aG docker ubuntu
        #sudo usermod -aG docker vagrant

	    echo "+-------------------------------------+"
	    echo "|                                     |"
	    echo "|      Installed docker               |"
	    echo "|                                     |"
	    echo "+-------------------------------------+"
		
	    echo "+-------------------------------------+"
	    echo "|                                     |"
	    echo "|      Vagrant setup completed        |"
	    echo "|                                     |"
	    echo "+-------------------------------------+"
    SHELL
end
