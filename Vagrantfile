# -*- mode: ruby -*-
# vi: set ft=ruby :

# set minimal Vagrant version
Vagrant.require_version ">= 1.5.0"

Vagrant.configure("2") do |config|
  config.ssh.forward_agent = true
  # see https://twitter.com/mitchellh/status/525704126647128064
  config.ssh.insert_key = false

  # Plugins section
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :machine
    config.cache.auto_detect = false
    config.cache.enable :apt
  end

  config.vm.box = "trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.network "private_network", ip: '172.16.3.10'
  config.vm.synced_folder '.', '/vagrant', disabled: true

  config.vm.provider "virtualbox" do |v|
    #v.gui = true
    v.cpus = 1
    v.memory = 1024
    v.customize ["modifyvm", :id, "--cpuexecutioncap", 50]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'playbooks/provisioning.yml'
    #ansible.extra_vars =
    #ansible.groups =

    #ansible.tags = []
    #ansible.skip_tags = ['']
    #ansible.verbose = 'vvvv'
    #ansible.raw_arguments = ['--check','--diff']
    end
end
