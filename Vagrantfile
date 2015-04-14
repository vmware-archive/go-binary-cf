# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

   config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install -y golang gccgo
     pushd /vagrant
        mkdir -p bin
        go build -o bin/test-server -ldflags "-s"
     popd

     echo "Build complete.  Now run: "
     echo "cf push some-app-name"
   SHELL
end
