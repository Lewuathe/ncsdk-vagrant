# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # NCSDK supports only ubuntu 16.04 LTS
  config.vm.box = "bento/ubuntu-16.04"

  config.vm.synced_folder "./ncsdk", "/home/vagrant/ncsdk"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.customize ["modifyvm", :id, "--usb", "on"]

    # Neural compute stick communicates via USB 3.0.
    vb.customize ["modifyvm", :id, "--usbxhci", "on"]
    vb.customize ["usbfilter", "add", "0",
      "--target", :id, 
      "--name", "Movidius",
      "--vendorid", "0x03e7"
    ]
  end
end
