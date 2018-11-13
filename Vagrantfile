# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "stakahashi/amazonlinux2"

  # Disable USB
  config.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--usb", "off"]
      vb.customize ["modifyvm", :id, "--usbehci", "off"]
  end

  # for web server
  config.vm.network "forwarded_port", guest: 80, host: 10080, auto_correct: true   # HTTP
  config.vm.network "forwarded_port", guest: 443, host: 10443, auto_correct: true  # HTTPS

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "site.yml"
    ansible.inventory_path = "vagrant"
    ansible.limit = 'all'
  end
end
