Vagrant.configure("2") do |config|
    # Load .env file with Vagrant and Ansible variables (see .env.dist)
    config.env.enable

    # Import Vagrant and Ansible variables from environment
    box_name = ENV['BOX_NAME']
    machine_name = ENV['VIRTUAL_MACHINE_NAME']
    host_name = ENV['HOST_NAME']
    app_name = ENV['APP_DIRECTORY']
    http_public_directory = ENV['HTTP_PUBLIC_DIRECTORY']

    config.vm.define box_name do |box|
        box.vm.provider :virtualbox do |v|
            v.name = machine_name
            v.customize ["modifyvm", :id, "--memory", 2048]
        end

        box.vm.box = "ubuntu/trusty64"

        box.vm.box_url = "https://vagrantcloud.com/ubuntu/trusty64/version/1/provider/virtualbox.box"

        box.vm.network :private_network, ip: "192.168.33.98"

        box.hostsupdater.aliases = [ host_name, "www." + host_name ]

        box.ssh.forward_agent = true

        box.vm.provision "ansible" do |ansible|
            ansible.playbook = "ansible/playbook.yml"
            ansible.limit = 'all'
            ansible.extra_vars = {
                app_name: app_name,
                server_name: host_name,
                http_public_directory: http_public_directory
            }
        end

        box.vm.synced_folder "./", "/vagrant", type: "nfs"
    end
end
