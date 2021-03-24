Vagrant.configure("2") do |config|

  config.vm.define :dev do |dev|
   dev.vm.box = "centos/7"
   dev.vm.hostname = "dev"
   dev.vm.network "private_network", type: "dhcp"
   dev.vm.network "public_network"
   #dev.vm.network  "forwarded_port", guest: 80, host: 9999, auto_correct: true
   #dev.vm.synced_folder "C:/Users/Alexander_Merkushkin/vagrant/share", "/share"
   #dev.vm.synced_folder "share/", "/share1/"
   dev.vm.synced_folder "C:\\Users/Alexander_Merkushkin/vagrant/share", "/home/vagrant/share", type: "nfs"
   #dev.vm.synced_folder "C:/Users/Alexander_Merkushkin/vagrant", "/home/vagrant/papka"
   dev.vm.provider "virtualbox" do |v|
     v.memory = "2048"
   end
   dev.vm.provision "shell", inline: <<-SHELL
     #yum update 
     #yum upgrade -y
     yum install epel-release -y
     yum install nginx -y
     systemctl start nginx
     systemctl enable nginx
   SHELL
  end

  config.vm.define :ci do |ci|
   ci.vm.box = "centos/7"
   ci.vm.hostname = "ci"
   ci.vm.network "private_network", type: "dhcp"
   ci.vm.network "public_network"
   #ci.vm.network  "forwarded_port", guest: 80, host: 9999, auto_correct: true
   ci.vm.synced_folder "C:\\Users/Alexander_Merkushkin/vagrant/share", "/home/vagrant/share", type: "nfs"
   #ci.vm.synced_folder "share/", "/share2/"
   #ci.vm.synced_folder "C:\Users\Alexander_Merkushkin\vagrant\share", "/share"
   #ci.vm.synced_folder "C:\Users\Alexander_Merkushkin\vagrant\nfsshare", "/nfsshare", type: "nfs"
   ci.vm.provider "virtualbox" do |v|
     v.memory = "4096"
   end
   ci.vm.provision "shell", inline: <<-SHELL
      #yum update
      #yum upgrade -y
      yum install java-1.8.0-openjdk-devel -y
   SHELL
  end
end
