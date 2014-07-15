# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = "precise32"

    config.vm.box_url = "http://files.vagrantup.com/precise32.box"

    # port forwarding, guest = vagrant, host = you
    config.vm.network :forwarded_port, guest: 80, host: 8080

    # run this provisioning script once booted
    config.vm.provision :shell, :path => "vagrant-install.sh"
    
# Sync Folder
config.vm.synced_folder "./", "/vagrant", id: "vagrant-root",
  owner: "vagrant",
  group: "www-data",
  mount_options: ["dmode=775,fmode=664"]

end
