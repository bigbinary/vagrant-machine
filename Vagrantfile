# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise64"

  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # Filesystem configuration. Share the current folder as "/vagrant" on the guest VM
  config.vm.synced_folder "./", "/vagrant"

  config.ssh.forward_agent = true

  config.vm.define "vmachine" do |cfg|

    #cfg.vm.network :forwarded_port, guest: 3000, host:3000

    cfg.vm.host_name = "vagrant.machine"

      cfg.vm.provision :ansible do |ansible|
        ansible.playbook = "provisioning/playbook.yml"
        ansible.verbose = 'vvv'
      end

  end
end
