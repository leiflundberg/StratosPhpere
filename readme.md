# Web dev environment
A simple LEMP-stack Vagrant box for web development with PHP. It is based on CentOS 8 and PHP 7.4.

## Usage
### Installation
To use this dev environment you must install VirtualBox and Vagrant on your system. 

https://www.virtualbox.org/wiki/Downloads

https://www.vagrantup.com/downloads

Once these two are installed you can simply run:

```
git clone https://github.com/leiflundberg/StratosPhpere.git
cd StratosPhere
./vus.sh
```

### Development
You may obviously change the Vagrantfile and tweak it to your liking, but if you have kept all of the values default:

**IP: 192.168.33.10**

**Username: vagrant**

**Password: vagrnat**

**nginx root folder: /usr/share/nginx/html**

**nginx config file: /etc/nginx/nginx.conf**

**Forwarded port localhost:42069 => (vagrant) 80**


Shared folder is between the current working directory (same as where the Vagrantfile is located) => /vagrant.
```
(host) . (vagrant guest) => /vagrant
```

## Troubleshooting

### Vagrant missing file id_rsa / SSH cannot connect
Have you remembered to generate an SSH-keypair? The file /home/$USER/.ssh/id_rsa must simply exist.
```
cd
touch .ssh/id_rsa
```
If you want to do this how you are supposed to: 
```
ssh-keygen -t rsa -C "your_email@example.com"

```

### Ubuntu 20.04 WARNING: The character device /dev/vboxdrv does not exist.
```
sudo apt-get install linux-headers-generic
sudo dpkg-reconfigure virtualbox-dkms
```

### mount: /vagrant: unknown filesystem type 'vboxsf'.
Make sure you are not on an older version of Vagrant, some Linux distrobutions have an outdated version in their repositories. You can check installed version:
```
vagrant --version 
```

### Synced folder trouble with Windows 10 as host OS:
https://stackoverflow.com/questions/40972345/vagrant-synced-folders-not-working-real-time-on-virtualbox

# Customization
## For nicer directory colors when using shared folders you can run: 

```
wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors
echo 'eval $(dircolors -b $HOME/.dircolors)' >> $HOME/.bashrc
. $HOME/.bashrc
```

