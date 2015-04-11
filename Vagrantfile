GUEST_ADDITION_VERSION = "4.3.20"
Vagrant.configure("2") do |c|
  c.berkshelf.enabled = false if Vagrant.has_plugin?("vagrant-berkshelf")
  c.vm.box = "opscode-ubuntu-12.04"
  c.vm.box_url = "https://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-12.04_chef-provisionerless.box"
  c.vm.hostname = "default-ubuntu-1204"
  c.vm.synced_folder ".", "/vagrant", disabled: true
  c.vm.provider :virtualbox do |p|
  end

  c.vbguest do |vbguest|
    vbguest.auto_update = false
    vbguest.iso_path = "http://download.virtualbox.org/virtualbox/#{GUEST_ADDITION_VERSION}/VBoxGuestAdditions_#{GUEST_ADDITION_VERSION}.iso"
  end

  c.vm.provision "shell", inline: "wget https://www.chef.io/chef/install.sh && sudo bash install.sh && rm install.sh"
end
