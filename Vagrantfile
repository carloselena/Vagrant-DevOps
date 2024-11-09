Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/jammy64"
    
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
    SHELL

    config.vm.network "forwarded_port", guest: 80, host: 8080
  
    config.vm.synced_folder "src", "/var/www/html", type: "virtualbox"
  end
  