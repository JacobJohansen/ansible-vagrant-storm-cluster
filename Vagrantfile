# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.1/centos65-x86_64-20131205.box"
  
#  config.vm.define "dev_box" do |dev|
#    dev.vm.box = "centOS65"
#    dev.vm.network :private_network, ip: "192.168.33.13"
#    dev.vm.provision "ansible" do |ansible|
#    	ansible.host_key_checking = false
#        ansible.inventory_path = "provisioning/dev"
#        ansible.playbook = "provisioning/dev_machine.yml"   
#    end
#  end  



  config.vm.define "zookeeper" do |zookeeper|
    zookeeper.vm.box = "centOS65"
    zookeeper.vm.network :private_network, ip: "192.168.33.11"
    zookeeper.vm.provision "ansible" do |ansible|
       ansible.host_key_checking = false
       ansible.inventory_path = "provisioning/dev"
       ansible.playbook = "provisioning/zookeeper_servers.yml"
    end
  end
  

  config.vm.define "nimbus" do |nimbus|
    nimbus.vm.box = "centOS65"
    nimbus.vm.network :private_network, ip: "192.168.33.10"
    nimbus.vm.provision "ansible" do |ansible|
        ansible.host_key_checking = false
        ansible.inventory_path = "provisioning/dev"
        ansible.playbook = "provisioning/nimbus_servers.yml"
    end
  end

  config.vm.define "supervisor01" do |supervisor01|
    supervisor01.vm.box = "centOS65"
    supervisor01.vm.network :private_network, ip: "192.168.33.12"
    supervisor01.vm.provision "ansible" do |ansible|
       ansible.host_key_checking = false
       ansible.inventory_path = "provisioning/dev"
       ansible.playbook = "provisioning/supervisor_servers.yml"
    end
  end
 
  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  #config.vm.network :forwarded_port, guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network :private_network, ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  # config.ssh.forward_agent = true

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider :virtualbox do |vb|
  #   # Don't boot with headless mode
  #   vb.gui = true
  #
  #   # Use VBoxManage to customize the VM. For example to change memory:
  #   vb.customize ["modifyvm", :id, "--memory", "1024"]
  # end
  #
  # View the documentation for the provider you're using for more
  # information on available options.

end
