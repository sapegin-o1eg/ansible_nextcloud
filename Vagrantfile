# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # General Vagrant VM configuration.
  config.vm.box = "ubuntu/bionic64"
  # config.vm.box = "geerlingguy/centos7"
  config.ssh.insert_key = false
  # config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 1536
    v.linked_clone = true
  end

  # Application server.
  config.vm.define "nc" do |app|
    app.vm.hostname = "nc.local"
    app.vm.network :private_network, ip: "192.168.60.4"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    config.vm.network "forwarded_port", guest: 80, host: 8087
  end
end
