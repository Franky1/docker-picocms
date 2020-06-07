# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    # config.vm.box = "debian/buster64"
    # config.vm.box = "metabarj0/DockerBox"
    config.vm.box = "generic/alpine312"
    config.vm.box_check_update = false

    # config.ssh.username = "vagrant"
    # config.ssh.password = "vagrant"
    # config.ssh.insert_key = false

    # plugin update disabled
    if Vagrant.has_plugin?("vagrant-vbguest")
      config.vbguest.auto_update = false
      # config.vbguest.remove_on_suspend = true
    end

    # TODO: disable plugin after first run!?
    # if Vagrant.has_plugin?("vagrant-vbguest")
    #   config.vbguest.remove_on_suspend = true
    # end

    config.vm.define "picocms" do |picocms|
      picocms.vm.hostname = "pico.test"
      picocms.vm.network "private_network", ip: "10.0.23.19"
      # picocms.vm.network "public_network", ip: "192.168.178.202"
      picocms.vm.synced_folder ".", "/vagrant", mount_options: ["iocharset=utf8"]

      # VirtualBox specific settings
      picocms.vm.provider "virtualbox" do |virtualbox|
        # friendly name of the virtual machine
        virtualbox.name = "PicoCMS"
        # Hide/show the VirtualBox GUI when booting the machine
        virtualbox.gui = true
        # Customize the amount of memory 8GB on the VM:
        virtualbox.memory = 2048
        # Use 2 CPUs in the VM:
        virtualbox.cpus = 2
      end

      # install netstat tools on the docker host machine
      # picocms.vm.provision "shell", inline: <<-SCRIPT
      #   apt-get update
      #   apt-get upgrade -y
      #   apt-get install net-tools -y
      # SCRIPT

      # update/upgrade/add net-tools, docker, docker-compose
      picocms.vm.provision "shell", inline: <<-SCRIPT
        apk update
        apk upgrade
        apk add net-tools
        apk add docker
        apk add docker-compose
        rc-update add docker boot
        service docker start
        cd /vagrant
        docker pull php:apache
        docker-compose build
        docker images
      SCRIPT
    end
  end
