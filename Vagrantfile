# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "debian/contrib-jessie64"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.synced_folder "dnevnik/", "/var/www/dnevnik", owner: 999, group: 999

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "bootstrap_server.yml"
    ansible.extra_vars = {
      vagrant: true
    }
  end

end
