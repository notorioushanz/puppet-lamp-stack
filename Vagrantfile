Vagrant.configure("2") do |config|

  # Enable the Puppet provisioner, with will look in manifests
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file = "default.pp"
    puppet.module_path = "modules"
  end

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "ubutnu/trusty64"

  # Forward guest port 80 to host port 8888 and name mapping
  config.vm.network "private_network", ip: "192.168.33.11"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 53, host: 5353, protocol: 'udp'

  config.vm.synced_folder "webroot/", "/vagrant/webroot/", :owner => "www-data"
end
