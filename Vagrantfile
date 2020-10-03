Vagrant.configure("2") do |config|

  config.vm.provider "Jenkins" do |d|
  config.vm.network "forwarded_port", guest: 8080, host: 8080
    d.image = "jenkins/jenkins:lts"
    args = "-p 8080:8080"
  end

  config.vm.provider "Gitlab" do |d|
  config.vm.network "forwarded_port", guest: 80, host: 80
    d.image = "gitlab/gitlab-ee:latest"
    args = "-p 80:80"
  end

  config.vm.provider "Nexus" do |d|
  config.vm.network "forwarded_port", guest: 8081, host: 8081
    d.image = "sonatype/nexus3"
    args = "-p 8081:8081"
  end

  config.vm.define "app" do |web|
    web.vm.box = "hashicorp/bionic64"
    config.vm.network "forwarded_port", guest: 3000, host: 3000
  end

end
