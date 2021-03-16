Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox"
  config.vm.box = "aakulov/bionic64"
  config.vm.provision "shell", path: "scripts/install_go.sh"
  config.vm.provision "shell", path: "scripts/build_hello.sh"
  config.vm.provision "shell", path: "scripts/test_hello.sh"
end
