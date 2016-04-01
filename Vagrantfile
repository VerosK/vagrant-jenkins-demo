# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "vStone/centos-7.x-puppet.3.x"

  config.vm.box_check_update = false

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  #config.vm.synced_folder "data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = 3192
    vb.cpus = 2

  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/site.yml"
    ansible.host_key_checking = false
    ansible.verbose = "v"
    ansible.sudo = true
    ansible.sudo_user = 'root'
    # if you want to fire ansible on all machines at parallel, use this!
    #ansible.limit = 'all'
  end
end
