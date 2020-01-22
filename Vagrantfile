# -*- mode: ruby -*-
# vi: set ft=ruby :
# Trident Ship Scaling reproducible environment prototype, started 10/4/18
# Prereqs:
# Vagrant: https://www.vagrantup.com/downloads.html
# Oracle VirtualBox: https://www.virtualbox.org/wiki/Downloads
# Select OS and define VM name

Vagrant.configure("2") do |config|
  config.vm.define "es01" do |es01|
    es01.vm.box = "centos/7"
    es01.vm.network "private_network", ip: "10.0.0.21"
    es01.vm.hostname = 'es01'
    es01.vm.provider "virtualbox" do |vb|
            vb.memory = "4096"
            vb.cpus = "2"
    end
    es01.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"
    es01.vm.provision "shell", inline: <<-SHELL
            cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end

  config.vm.define "es02" do |es02|
    es02.vm.box = "centos/7"
    es02.vm.network "private_network",ip:"10.0.0.22"
    es02.vm.hostname = 'es02'
    es02.vm.provider "virtualbox" do |vb|
            vb.memory = "4096"
            vb.cpus = "2"
    end
    es02.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"
    es02.vm.provision "shell", inline: <<-SHELL
            cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end

  config.vm.define "es03" do |es03|
    es03.vm.box = "centos/7"
    es03.vm.network "private_network",ip:"10.0.0.23"
    es03.vm.hostname = 'es03'
    es03.vm.provider "virtualbox" do |vb|
            vb.memory = "4096"
            vb.cpus = "2"
    end
    es03.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"
    es03.vm.provision "shell", inline: <<-SHELL
            cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
end