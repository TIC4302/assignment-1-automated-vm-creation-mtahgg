Vagrant.configure("2") do |config|
  
  config.vm.define "attacker" do |attacker|
    config.vm.box = "kalilinux/rolling"
    config.vm.hostname = "attacker"
    config.vm.define "attacker"
    config.vm.provider :virtualbox do |vb|
       vb.name = "attacker"
       vb.memory = "2048"
       config.vm.network "private_network", :type => 'dhcp', :adapter => 2
      end
  end

  config.vm.define "victim" do |victim|
    victim.vm.box = "ubuntu/trusty64"
    victim.vm.hostname = "victim"
    victim.vm.define "victim"
    victim.vm.provider :virtualbox do |vb|
        vb.name = "victim"
        vb.memory = "2048"
        config.vm.network "private_network", :type => 'dhcp', :adapter => 2
      end
  end

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
end
