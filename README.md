# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

1) Install kali linux either in partition or virtual box or in live mode
2) Investigate on the various categories of tools as follows
3) Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/15d275d8-8506-4a5f-aeb4-9598ed95c940)

Invoke msfconsole:

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/c5597a4a-beaa-486c-9b2a-935d463ea482)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/17d2ad76-b328-4ec6-a10f-d4ce49c0476d)

Port Scanning:

Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/fb87edb5-a455-4124-9032-11b7388c5c7e)

USE the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24


## OUTPUT:

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/aab8ef4d-4cfa-4fbe-8058-ef7f4c48569f)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/d25b97ad-05b1-4e14-bf14-3c4603e089ad)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

## OUTPUT

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/134b46a5-ad28-4237-bdc1-1f5c96438a1c)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

## MYSQL ENUMERATION

Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/ebfd5dbc-1b76-46e0-b023-f1662ea7e7ec)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/7d5f3999-42cb-4f88-bab9-f4012a483d9b)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/ea815e20-383a-4d58-af3a-39428260257b)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/2ad1bd39-f4df-4848-a7c6-1d14886d1fc9)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/25843318-abfc-4158-9bb0-fe77d1c6d034)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/Monisha-11/Metasploit-for-reconnaissance/assets/93427240/b8042afe-1c73-43aa-ae94-5c9c577e33f5)


## RESULT:

The Metasploit framework for reconnaissance is  examined successfully
