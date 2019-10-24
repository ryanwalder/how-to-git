# Example Vagrantfile
#
# NOTE: This Vagrantfile isn't actually meant to do anything, it's just the
# "code" we're using for the examples in the repo.

Vagrant.configure("2") do |config|
  config.vm.box = "precise32"
  config.vm.hostname = "myprecise.box"
  config.vm.network :private_network, ip: "192.168.0.42"

  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--cpuexecutioncap", "25",
      "--memory", "2048",
    ]
  end
end
