Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true

### Jenkins VM  ####
  config.vm.define "jenkins" do |jenkins|
    jenkins.vm.box = "geerlingguy/ubuntu1804"
    jenkins.vm.hostname = "jenkins"
    jenkins.vm.network "private_network", ip: "192.168.33.15"
    jenkins.vm.provision "shell", path: "jenkins-setup.sh"
    jenkins.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
      end

  end

### Sonar VM  ####
  config.vm.define "sonar" do |sonar|
    sonar.vm.box = "geerlingguy/ubuntu1804"
    sonar.vm.hostname = "sonar"
    sonar.vm.network "private_network", ip: "192.168.33.14"
    sonar.vm.provision "shell", path: "sonar-setup.sh"
    sonar.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
      end
  end


### NEXUS VM ###
   config.vm.define "nexus" do |nexus|
    nexus.vm.box = "geerlingguy/centos7"
    nexus.vm.hostname = "nexus"
    nexus.vm.network "private_network", ip: "192.168.33.13"
    nexus.vm.provision "shell", path: "nexus-setup.sh"
    nexus.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
   end
   end
end
