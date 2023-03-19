





#Saving an existing Vagrant box:
1 - If your Vagrant box is still running, make sure to shut it down first:
vagrant halt

2 Execute create Vagrant box package:
Export virtual box to package as a base box (virtual only) 
nassi@DESKTOP-U7TV2ED MINGW64 ~/OneDrive/Documents/042023_kubernetes_formation/vagrantFile
$ vagrant package --base kubmaster --output kubemaster_ubuntu_xenial_2023.box
==> kubmaster: Clearing any previously set forwarded ports...
==> kubmaster: Exporting VM...
==> kubmaster: Compressing package to: C:/Users/nassi/OneDrive/Documents/042023_kubernetes_formation/vagrantFile/kubemaster_ubuntu_xenial_2023.box


## Removing an existing Vagrant box:
If your Vagrant box is still running, make sure it is shutdown:
vagrant halt
      

    
Execute destroy Vagrant box:
vagrant destroy
      
    
Note: If you received this error message:
Vagrant is attempting to interface with the UI in a way that requires
a TTY. Most actions in Vagrant that require a TTY have configuration
switches to disable this requirement. Please do that or run Vagrant
with TTY.
      

... execute this command instead:
vagrant destroy -f
      

Backup the existing Vagrant config file and delete it:
cp Vagrantfile Vagrantfile.bak
rm Vagrantfile


Delete the actual Vagrant box image:    
rm ~/.vagrant.d/boxes/centos7drupal
      

    
## Restoring saved Vagrant box:
Execute add Vagrant box:

      

vagrant box add kubemaster_ubuntu_xenial_2023 kubemaster_ubuntu_xenial_2023.box
or 
vagrant box add kubemaster kubemaster_ubuntu_xenial_2023.box

Initialize your Vagrant box:
vagrant init kubemaster_ubuntu_xenial_2023
      

    
That command will create generic Vagrant config file. If you prefer to use the previous Vagrant config file, execute the following commands:

      
rm Vagrantfile
mv Vagrantfile.bak Vagrantfile
      

    
Boot your Vagrant box:
vagrant up
