# Web dev environment
A simple LEMP-stack Vagrant box for web development with PHP. It is based on CentOS 8 and focuses on using recent, official versions of software.

## Usage
### Installation
To use this dev environment you must install VirtualBox and Vagrant on your system. 

https://www.virtualbox.org/wiki/Downloads

https://www.vagrantup.com/downloads

Once installed you can simply run:

# TODO ADD LINK HERE

### Development
You may obviously change the Vagrantfile and tweak it to your liking, but if you have kept all of the values default:

IP: 192.168.33.10

Shared folder is between the current working directory (same as where the Vagrantfile is located) => /vagrant.

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

### Synced folder trouble with Windows 10 as host OS:
https://stackoverflow.com/questions/40972345/vagrant-synced-folders-not-working-real-time-on-virtualbox

# Customization
## For nicer directory colors when using shared folders you can run: 

```
wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors
echo 'eval $(dircolors -b $HOME/.dircolors)' >> $HOME/.bashrc
. $HOME/.bashrc
```

