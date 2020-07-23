# Web dev environment
A dead-simple LEMP-stack Vagrant box for web development with PHP. It is based on CentOS 8.1, Nginx, MariaDB and PHP 7.4.

## Usage
### Installation
To use this dev environment you must install VirtualBox and Vagrant on your system. 

https://www.virtualbox.org/wiki/Downloads

https://www.vagrantup.com/downloads

Once these two are installed you can simply run:

```
git clone https://github.com/leiflundberg/StratosPhpere.git
cd StratosPhere
vagrant up && vagrant ssh
```

### Development
You may obviously change the Vagrantfile and tweak it to your liking, but if you have kept all of the values default:

**localhost:42069 => (vagrant):80**

**Username: vagrant**

**Password: vagrant**

**nginx root folder: /usr/share/nginx/html**

**nginx config file: /etc/nginx/nginx.conf**


Shared folder is between the current working directory (same as where the Vagrantfile is located) => /vagrant.
```
(host) . (vagrant guest) => /vagrant
```

## Troubleshooting

### Vagrant missing file id_rsa / SSH cannot connect / retrying...
#### Don't care about SSH-keypairs? 
Add the following line to your Vagrantfile:

```
config.ssh.insert_key = false
```

#### Care about SSH-keypairs?
Does the file exist? For Vagrant to accept a keypair the file /home/$USER/.ssh/id_rsa must simply exist.

```
cd
touch .ssh/id_rsa
```

If you want to generate a SSH-keypair: 

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

Alternatively you might need to install the file extension: 

```
sudo apt install build-essential dkms linux-headers-$(uname -r)
```

### Synced folder trouble
Sometimes synced folders are not working in real time on Virtualbox, in particular under Windows 10 as host OS. You may use rsync to fix this. 

https://www.vagrantup.com/docs/synced-folders/rsync.html

You can also use the NFS file system:

```
config.vm.synced_folder ".", "/home/ubuntu/qb-online", type: "nfs"
```

# Customization
## Zsh and oh-my-zsh

chsh -s $(which zsh)

## For nicer directory colors when using shared folders you can run: 

```
wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors
echo 'eval $(dircolors -b $HOME/.dircolors)' >> $HOME/.bashrc
. $HOME/.bashrc
```


