# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "leiflundberg/StratosPhpere"
  config.vm.network "forwarded_port", guest: 80, host: 42069
end
