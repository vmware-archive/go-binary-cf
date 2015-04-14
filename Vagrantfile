# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

   config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install -y golang gccgo
     pushd /vagrant
	go build -o bin/test-server -compiler gccgo -gccgoflags "-static-libgo"
     popd

     echo "Build complete.  Now run: "
     echo "cf push test-server -b https://github.com/ryandotsmith/null-buildpack -s cflinuxfs2"
   SHELL
end
