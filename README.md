# OSCP-pen-200
resume of all the course
## 1-getting Comfortable with kali linux
To change the password : passwd
To know the user : whoami
To excute commande as root : sudo 
2-Linux fileSystem :
/bin/  => contain basic programmes
/sbin/  => contain system programmes
/etc/  => contain configuration file
/tmp/  => contain temparary file which be deleted when boot

3 -basic commande :
man +commande  =>  to show the documentation of the commande 
man -k 'command or regular expression'  / apropos 'commande or regular '  =>  to search a commande
ls -a  =>  show all file include hidden
cd  => to go to directory
cd ~  =>  to go to home directory
pwd  =>  to show the directory
mkdir name_directory  =>  to create directory 
rm -rf name_directory  =>  to delete directory
mkdir -p {a,b,c,d}  =>  to create multiple directory

4 - finding files on kali linux :
which name  =>  search in bin sbin directories.
locate name   =>  search in database locate.db
find / -name name  =>  for recursive searche of file 

5-services in linux :
systemctl list-unit-files  =>  to show the status of all services
sudo systemctl start ssh   =>  to start the ssh service
sudo systemctl enable ssh  => to start automaticaly when boot time
sudo systemctl start apache2   =>  to start the http service

6-update and upgrade :
sudo apt update  =>  to update apt database of version of your packages

sudo apt install package
sudo apt upgrade package  =>  to upgrade the package
sudo apt remove --purge package
apt-cache search neme # to serach if the name package  is installed 

sudo dpkg -i ./package.deb   => to install package from file.deb

