# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "leiflundberg/StratosPhpere"
  # Remember to update this to your desired version
  config.vm.box_version = "1.0.2"
  # Only using port forwarding, if you want a static ip, install virtualbox guest additions
  config.vm.network "forwarded_port", guest: 80, host: 42069
  # This is with rsync, if you want NFS, install virtualbox guest additions
  config.vm.synced_folder ".", "/vagrant", disabled: true
  # No SSH keys needed, no sudo password on local machine
  config.ssh.insert_key = false

  config.vm.provision "shell", inline: <<-SHELL
    # Helper tools
    sudo yum update && sudo yum -y install wget git nano
    sudo dnf install util-linux-user
    # Installing Symfony
    wget https://get.symfony.com/cli/installer -O - | bash
    export PATH="$HOME/.symfony/bin:$PATH"
    # Installing PHP extensions for Symfony
    sudo yum -y install php-xml php-dom php-mbstring php-posix php-intl php-pdo php-opcache
    symfony check:requirements
    
    # Installing Zsh and oh-my-zsh
    # sudo yum intall zsh
    # zsh --version

    # Splashscreen
  
  SHELL

end
