# Web dev environment
A dead-simple LEMP-stack Vagrant box for web development with PHP. It is based on CentOS 8.1, Nginx, MariaDB and PHP 7.4.

## Usage
### Installation
To use this dev environment you must have VirtualBox and Vagrant installed on your system. 

https://www.virtualbox.org/wiki/Downloads

https://www.vagrantup.com/downloads

Once these two are installed you can simply run:

```
git clone https://github.com/leiflundberg/StratosPhpere.git
cd StratosPhere
vagrant up && vagrant ssh
```

### Development
You are obviously welcome to change the Vagrantfile and tweak it to your liking, but if you are using the included Vagrantfile:

**localhost:42069 => (vagrant):80**

**Username: vagrant**

**Password: vagrant**

**nginx root folder: /usr/share/nginx/html**

**nginx config file: /etc/nginx/nginx.conf**


Shared folder is between the current working directory (same as where the Vagrantfile is located) => /vagrant.
```
(host) . (vagrant guest) => /vagrant
```

# Customization
## For nicer directory colors when using shared folders you can run: 

```
wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors
echo 'eval $(dircolors -b $HOME/.dircolors)' >> $HOME/.bashrc
. $HOME/.bashrc
```


