#ansible-php-nginx
A Vagrant/Ansible configuration for quickly and easily creating and provisioning Vagrant boxes with a basic PHP/Nginx 
setup.

##Usage
- make sure that vagrant-hostsupdater and vagrant-env are installed (```vagrant plugin install vagrant-hostsupdater 
&& vagrant plugin install vagrant-env```)
- create a .env file based on .env.dist and adjust the Vagrant box identifier, Virtualbox machine name, server/hostname, 
app name and HTTP public directory 
- run ```vagrant up```

##Dependencies
- Vagrant-hostsupdater
- Vagrant-env