# Default credentials
#   Shell: vagrant / vagrant

VAGRANTFILE_API_VERSION = "2"

##-- Global config -------------------------------------------------------------
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Don't update the sshkey
  config.ssh.insert_key = false

  # Don't update guest additions
  config.vm.box_check_update = false
  config.vbguest.auto_update = false

  # Private IP Address (eth1)
  # private_ip =

  ##-- Machine -----------------------------------------------------------------
  config.vm.define "rhel84gui" do |rhel84gui|
    rhel84gui.vm.box = "rhel84"
    # rhel84gui.vm.box = "victorbrca/rhel84-gui"
    # rhel84gui.vm.network "private_network", ip: private_ip

    # Set the synced folder
    rhel84gui.vm.synced_folder ".", "/vagrant", type: "virtualbox"

    ##-- Provider --------------------------------------------------------------
    rhel84gui.vm.provider "virtualbox" do |vb|
      # Use internal DNS from host
      vb.customize [ "modifyvm", :id, "--natdnshostresolver1", "on" ]
      vb.name = "rhel84-gui"
      vb.memory = "1024"
    end

  end
end
