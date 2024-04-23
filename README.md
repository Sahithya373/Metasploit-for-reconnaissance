# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

## OUTPUT:
Find out the ip address of the attackers system
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/56d5895f-417c-41a4-8a12-c8bfc840b08f)

Invoke msfconsole:
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/2b8cb769-3720-4335-bdfb-454596175f39)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/67ac7729-d4d6-4aa6-8622-430d1ece37bc)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/b4abeda3-5f54-4244-9670-32eb20cbf591)

use db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later. scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/6da7df24-14f6-444e-82af-5244354c1827)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/3df95d14-d517-4198-a5e5-5f83f0c62e3c)

![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/f0d4d90c-448a-421e-8319-661157db635d)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/63595f43-0330-44a4-bfa1-f154403daab4)

The info command provides information regarding a module or platform
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/8ca77281-af95-4032-9c31-1812fc34cf07)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/e4d8c3d9-dc6a-49f2-b787-22caeba45fdb)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/33e332a2-ed00-44ac-a2b9-60fda94df1e8)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/b8332d3d-800f-4545-9bb7-3c73ded7cacb)

Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/4a5d48b2-5f5d-4e01-933f-8c388a58d7eb)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/339f29e4-c3ce-4c81-b42c-01775ba8097e)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/Sahithya373/Metasploit-for-reconnaissance/assets/147017926/ca7a1a2e-c999-4eb2-8430-2f8047d8f022)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
