Vagrant.configure("2") do |config|
  config.vm.define "iis01" do |iis01|
    iis01.vm.box = "davydany/Windows2016"
    iis01.vm.box_check_update = false
    iis01.vm.network "private_network", ip: "192.168.33.10"
    iis01.vm.provision :shell, inline: "Add-WindowsFeature Web-Server"
  end
  config.vm.define "iis02" do |iis02|
    iis02.vm.box = "davydany/Windows2016"
    iis02.vm.box_check_update = false
    iis02.vm.network "private_network", ip: "192.168.33.11"
    iis02.vm.provision :shell, inline: "Add-WindowsFeature Web-Server"
  end
  config.vm.define "lb" do |lb|
    lb.vm.box = "ubuntu/trusty64"
    lb.vm.box_check_update = false
    lb.vm.network "private_network", ip: "192.168.33.12"
    lb.vm.provision :shell, inline: "sudo apt-get update -y"
    lb.vm.provision :shell, inline: "sudo apt-get install nginx -y"
    lb.vm.provision :shell, inline: "sudo service nginx start"
    lb.vm.provision "file", source: "nginx.conf", destination: "~/nginx.conf"
    lb.vm.provision :shell, inline: "sudo mv /home/vagrant/nginx.conf /etc/nginx/nginx.conf -f"
    lb.vm.provision :shell, inline: "sudo service nginx reload"
  end
end

# https://vegibit.com/how-to-provision-nginx-using-vagrant/