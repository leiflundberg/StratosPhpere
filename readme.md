# Web dev environment
A dead-simple LEMP-stack Vagrant box for web development with Symfony. It is based on Red Hat CentOS 8.1, Nginx 1.14.1, MySQL 10.3.17-MariaDB and PHP 7.4.8. Other included software: wget, git, nano, the Symfony CLI alongside all suggested PHP extensions and Composer.

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
