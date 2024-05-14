Vagrant.configure("2") do |config|
    config.vm.box = "generic/ubuntu2204"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
        vb.cpus = 2
    end

    config.vm.network "private_network", ip: "192.168.56.10"

    config.vm.provision "file", source: "#{Dir.pwd}/ssh/id_ed25519.pub", destination: "/home/vagrant/.ssh/id_ed25519.pub"
    config.vm.provision "shell", inline: "cat /home/vagrant/.ssh/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys"
end