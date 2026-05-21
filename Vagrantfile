Vagrant.configure("2") do |config|
  config.vm.synced_folder ".", "/vagrant", type: "rsync"
  config.vm.box = "almalinux/9"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
  end

  config.vm.define "nginx_node" do |node|
    node.vm.hostname = "nginx-server"
    node.vm.network "private_network", ip: "192.168.56.101"
  end

  config.vm.define "apache_node" do |node|
    node.vm.hostname = "apache-server"
    node.vm.network "private_network", ip: "192.168.56.102"
  end

  config.vm.define "mysql_node" do |node|
    node.vm.hostname = "mysql-server"
    node.vm.network "private_network", ip: "192.168.56.103"
  end

    config.vm.provision "ansible_local" do |ansible|

      ansible.playbook = "/vagrant/site.yml"
      ansible.compatibility_mode = "2.0"
      ansible.provisioning_path = "/vagrant"
      ansible.groups = {
        "nginx" => ["nginx_node"],
        "apache" => ["apache_node"],
        "mysql" => ["mysql_node"]
      }
      ansible.extra_vars = {
        "docker_app_user_home" => "/home/vagrant", "app_path" => "/home/vagrant/albatross-tester"
      }
    end
  end

