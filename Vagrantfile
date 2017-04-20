Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 8545, host: 8545 #mainnet
  #config.vm.network "forwarded_port", guest: 18333, host: 18333 #testnet

  config.vm.network "forwarded_port", guest: 8545, host: 8545 #mainnet RPC
  #config.vm.network "forwarded_port", guest: 18332, host: 18332 #testnet RPC

  #config.vm.network "public_network", ip: 192.168.1.201

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    sudo apt-get -y install software-properties-common
    sudo add-apt-repository -y ppa:ethereum/ethereum
    sudo apt-get -y update
    sudo apt-get -y install ethereum
    geth account new
  SHELL
end
