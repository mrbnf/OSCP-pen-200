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
 
 ## commande line fun :
 2-commande line fun :
environment variable:
env => to show all the variables

echo $name_var => to show the containte of the variable

name_var = "data"  => to implement variable localy

export name_var="data"  => to implement variable and show it from other bash

history => to show history of commande entered

!commande_number => to excute the commande number

!! => to excuter the final commande



tail -n 3 .bash_history => to give 3 final commande in bash history

ctrl + r  => to search for commande the enter to excute 




redirection : STDIN, STDOUT, and STDERR are defined as 0, 1, and 2 respectively. can be addet before the > .for the condition

echo "hello world" > h.txt  => create the file with the text or replace if exsist

cat h.txt  => show the file

echo "new line" >> h.txt  => add the line to the file

piping :

commande 1| comande 2  =>  apply comannde 2 to result of commande 1



grep text => show all line contain text 

grep -v text => show all line not contain text

echo "i am aziz" | sed 's/aziz/abdelaaziz/'  => to remplace aziz with abdelaaziz and in general to edit 

cut -d ":" -f 1 /etc/passwd => to show text before : for each line or cutting


echo "hello::world::iamaziz" | awk -F "::" '{print $1,$3}' => awk same with cut with multiple digit seperator

wc -l file.txt => number of line

sort -u => eliminate double

uniq -c => add the number of occurence




editing files :

nano 


vi

comparing files :

comm file1 file2 => must be sorted

diff -c file1 file2 => like comm

vimdiff file1 file2 => open vi and show the two files

managing process :

background process or excute in background : add & to the end of commande

job control :

jobs => give jobs running in the current terminal

fg %jobNumber => to return job to foreground

process control :

ps -ef => to show all process

ps -FC leafpad => to show specific process

kill process id => to delete and stop process

file and commande monitoring :

sudo tail -f /var/log/apache2/access.log => to show on real time change in file

watch -n 10 -d commande => to run commande every 10 seconds


downlaoding files :

wget  => to downlaod files

curl => to downlaod or uplaod

axel => for downlaod with multiple conneection


costimazing the bash environment :

alias lsa="ls -la" => to define a commande







