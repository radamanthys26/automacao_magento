Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "automacao-magento"
  config.vm.network "private_network", ip: "192.168.33.25"

  # Configuração VirtualBox
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "4096"
    vb.cpus = 2
    vb.customize ["modifyvm", :id, "--name", "automacao-magento"]
  end

  # Playbook do ansible
  config.vm.synced_folder ".", "/vagrant", type: 'virtualbox'

  # Provisioning
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.verbose = "vvv"
  end

  # Configurações da extras
  config.vm.provision "shell", inline: <<-SHELL
    #echo "sudo su -" >> .bashrc
    echo $'[all] \n192.168.33.25' > /etc/ansible/hosts
    echo $'[defaults] \nhost_key_checking = false' > /etc/ansible/ansible.cfg
  SHELL
end
