# Example Vagrantfile
#
# NOTE: This Vagrantfile isn't actually meant to do anything, it's just the
# "code" we're using for the examples in the repo.

disk = './secondDisk.vdi'

Vagrant.configure("2") do |config|
  config.vm.box = "xenial64"
  config.vm.hostname = "cs-vagrant-test-xenial-01.gel.zone"
  config.vm.network :private_network, ip: "192.168.66.42"

  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--cpuexecutioncap", "50",
      "--memory", "512",
    ]
    vb.customize ['createhd', '--filename', disk, '--variant', 'Fixed', '--size', 20 * 1024]
    vb.customize ['storageattach', :id,  '--storagectl', 'SATAController', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', disk]
  end
end
