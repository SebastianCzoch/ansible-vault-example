hostname            = 'example'
ram                 = 512
ansibleSkipTags     = Array.new

Vagrant.configure("2") do |config|
    config.vm.box = "debian/wheezy64"

    config.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--name", hostname, "--memory", ram]
        vb.customize ["modifyvm", :id, "--cpus", "2"]
    end

    # Provision
    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "provision/site.yml"
        ansible.ask_vault_pass = true
    end
end
