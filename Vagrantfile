Vagrant.configure("2") do |config|
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "Ansible/playbook.yml"
  end
  config.vm.provision "file", source: "Docker", destination: "$HOME/"

  config.vm.define "wp1" do |wp1|
    wp1.vm.network "public_network", ip: "172.16.1.100"
    wp1.vm.box = "bento/ubuntu-20.04"
    wp1.vm.provider "virtualbox" do |a|
      a.cpus = 2
      a.memory = 1024
    end
  end

  config.vm.define "wp2" do |wp2|
    wp2.vm.network "public_network", ip: "172.16.1.101"
    wp2.vm.box = "bento/ubuntu-20.04"
    wp2.vm.provider "virtualbox" do |b|
      b.cpus = 2
      b.memory = 1024
    end
  end

  config.vm.define "nginx" do |nginx|
    nginx.vm.network "public_network", ip: "172.16.1.102"
    nginx.vm.box = "bento/ubuntu-20.04"
    nginx.vm.provider "virtualbox" do |d|
      d.cpus = 2
      d.memory = 1024
    end
  end

  config.vm.define "db" do |db|
    db.vm.network "public_network", ip: "172.16.1.103"
    db.vm.box = "bento/ubuntu-20.04"
    db.vm.provider "virtualbox" do |c|
      c.cpus = 2
      c.memory = 2048
    end
  end
end
