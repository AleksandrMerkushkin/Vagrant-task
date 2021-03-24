Task
1.	Install Virtualbox
2.	Install Vagrant
3.	Initialize new Vagrant project
4.	Update configuration to use specific vagrant box
5.	Configure multiple VM’s in single Vagrantfile (2 VM’s)
6.	First VM should have 2GB RAM, second – 4GB RAM
7.	All VM’s should have 2 network interfaces so that both Internet and internal communication works
8.	Share host directory in 2 ways
9.	Configure provisioning with shell:
-	vm1: installing nginx (forward proxy to vm2/tomcat)
-	vm2: installing tomcat
Check
1.	Virtualbox and Vagrant are installed
2.	New Vagrant project created
3.	2 VM’s are bootstrapped using single “vagrant up” command
4.	2 VM’s have different RAM settings
5.	Each VM has 2 different network interfaces
6.	Each VM has shared directory from host
7.	Provisioning with shell is configured
8.	Tomcat is available from VM1
