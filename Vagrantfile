# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "leiflundberg/StratosPhpere"
  config.vm.box_version = "1.0.3"
  # Only using port forwarding, if you want a static ip, install virtualbox guest additions
  config.vm.network "forwarded_port", guest: 80, host: 42069
  # This uses rsync, if you want NFS for example, install virtualbox guest additions
  config.vm.synced_folder ".", "/vagrant", disabled: true
  # Change this line if you wish to use SSH keypairs
  config.ssh.insert_key = false

  config.vm.provision "shell", inline: <<-SHELL
    # Helper tools
    sudo yum update && sudo yum -y install wget git nano
    # Installing Symfony
    wget https://get.symfony.com/cli/installer -O - | bash
    export PATH="$HOME/.symfony/bin:$PATH"
    # Installing PHP extensions for Symfony
    sudo yum -y install php-xml php-dom php-mbstring php-posix php-intl php-pdo php-opcache
    symfony check:requirements
  SHELL

end
