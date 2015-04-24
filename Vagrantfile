# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "win7IE10_with_winRM"
  # config.vm.box_url = "http://aka.ms/vagrant-win7-ie10"
  config.vm.box_url = "file:////morpheus/pub-Transfer/t/twierzchowski/vagrant_box/package.box"
  config.vm.guest = :windows
  config.vm.communicator = "winrm"
  config.winrm.username = "IEUser"
  config.winrm.password = "Passw0rd!"
  config.vm.boot_timeout = 300
  
  config.vm.network :forwarded_port, guest: 5985, host: 55985, id: "winrm", auto_correct: true
  #config.vm.network "private_network"
  
  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = "1024"
    vb.cpus = 2
    vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
  end
  
  config.vm.provision "shell", inline: "choco install ruby1.9 -y"
  config.vm.provision "shell", inline: "choco install ruby.devkit -y"
  config.vm.provision "shell", inline: "choco install cmder -y"
  config.vm.provision "shell", inline: "choco install firefox -y"
  config.vm.provision "shell", inline: "choco install nodejs -y"
  config.vm.provision "shell", inline: "Start-Process \"c:\\tools\\Ruby193\\bin\\gem.bat\"   \"install bundler\""
  config.vm.provision "shell", inline: "Start-Process \"c:\\tools\\Ruby193\\bin\\gem.bat\"   \"update --system\""
end
