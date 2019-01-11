# Example Vagrantfile
#
# NOTE: This Vagrantfile isn't actually meant to do anything, it's just the
# "code" we're using for the examples in the repo.

Vagrant.configure("2") do |config|
  config.vm.box = "xenial64"
  config.vm.hostname = "cs-vagrant-test-xenial-01.gel.zone"
  config.vm.network :private_network, ip: "192.168.66i.42"

  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--cpuexecutioncap", "50",
      "--memory", "256",
    ]
  end
end
