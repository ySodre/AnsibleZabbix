Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"


  config.vm.define "zabbix" do |zabbix|
    zabbix.vm.network "public_network", ip: "192.168.10.105"
    zabbix.vm.provision "shell", path: "scripts/zabbix.sh"

  end

  config.vm.define "controler" do |control|
    control.vm.network "public_network"
    control.vm.provision "shell", path: "scripts/control.sh"
    control.vm.synced_folder "ansible", "/var/ansible"
  end

end