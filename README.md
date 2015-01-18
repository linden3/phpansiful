#ansible-php-nginx
A Vagrant/Ansible configuration for quickly and easily creating and provisioning Vagrant boxes with a basic PHP/Nginx 
setup.

##Usage
- make sure that vagrant-hostsupdater and vagrant-env are installed (```vagrant plugin install vagrant-hostsupdater 
&& vagrant plugin install vagrant-env```)
- create a .env file based on .env.dist and add the Vagrant box identifier, Virtualbox machine name and hostname 
- run ```vagrant up```

##Dependencies
- Vagrant-hostsupdater
- Vagrant-env