Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", type: "dhcp"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y build-essential libssl-dev
  SHELL

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    curl -so- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
    source ~/.bashrc
    export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
    nvm install 7.10.0 2>&1 > /dev/null
  SHELL
end
