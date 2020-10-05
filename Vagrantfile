Vagrant.configure("2") do |config|

  config.vm.define "jenkins" do |jenkins|
    config.vm.provider "docker" do |d|
    config.vm.network "forwarded_port", guest: 8080, host: 8080
      d.image = "jenkins/jenkins:lts"
      args = "-p 8080:8080"
    end
  end
  
  config.vm.define "nexus" do |nexus|
    config.vm.provider "docker" do |d|
    config.vm.network "forwarded_port", guest: 8081, host: 8081
      d.image = "sonatype/nexus3"
      args = "-p 8081:8081"
    end
  end

  config.vm.define "gitlab" do |gitlab|
    config.vm.provider "docker" do |d|
    config.vm.network "forwarded_port", guest: 80, host: 80
      d.image = "gitlab/gitlab-ee:latest"
      args = "-p 80:80"
    end
  end
  
  config.vm.define "app" do |app|
      app.vm.box = "hashicorp/bionic64"
      config.vm.network "forwarded_port", guest: 3000, host: 3000
    end
  end

end
