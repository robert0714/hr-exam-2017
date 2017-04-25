# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  if (/cygwin|mswin|mingw|bccwin|wince|emx/ =~ RUBY_PLATFORM) != nil
    config.vm.synced_folder ".", "/vagrant", mount_options: ["dmode=700,fmode=600"]
  else
    config.vm.synced_folder ".", "/vagrant"
  end
  config.vm.define "hr-exam" do |d|
    d.vm.box ="ubuntu/trusty64"
    d.vm.hostname = "hr-exam"
#   d.vm.network "private_network", ip: "192.168.57.87"
   d.vm.network "public_network", bridge: "eno4", ip: "192.168.57.87", auto_config: "false", netmask: "255.255.255.0" , gateway: "192.168.57.1"
   default_router = "192.168.57.1"
    d.vm.provision :shell, path: "scripts/bootstrap4Ubuntu_ansible.sh"
    d.vm.provision :shell, inline: "PYTHONUNBUFFERED=1 ansible-playbook /vagrant/ansible/exam.yml -c local"
    d.vm.provider "virtualbox" do |v|
      v.cpus = 2
      v.memory = 2048
    end
  end   
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end
end
