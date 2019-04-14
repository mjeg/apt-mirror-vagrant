
Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/bionic64"

  config.vm.provision :shell, :inline => "sed -i 's|deb http://archive.ubuntu.com.ubuntu|deb mirror://mirrors.ubuntu.com/mirrors.txt|g' /etc/apt/sources.list"
  config.vm.provision "shell", inline: "sed -i '/deb-src/d' /etc/apt/sources.list"
  config.vm.provision "shell", inline: "apt-get update -y"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end

end
