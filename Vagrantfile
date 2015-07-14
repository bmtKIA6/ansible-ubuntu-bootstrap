VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "public_network"

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end

  #
  # Map the current box to the "dev" group in ansible
  #
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    #ansible.inventory_path = "vagrant_hosts"
    ansible.verbose = "vvvv"
    ansible.groups = {
      "dev" => ["default"]
    }
  end

end
