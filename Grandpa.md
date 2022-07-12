Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/178387165-0c52e0fb-0056-4507-9f51-e20af3492088.png)


The web server gives us an error.

![image](https://user-images.githubusercontent.com/93418272/178387180-99150725-187c-4594-9003-cc4c486ce015.png)


Run a dirb scan to find for hidden directories. 

![image](https://user-images.githubusercontent.com/93418272/178387192-5c9b30e4-50c9-4bc6-9882-fc92a7cd679e.png)


Searchsploit Microsoft IIS 6.0.

![image](https://user-images.githubusercontent.com/93418272/178387213-a21d9f38-5f97-4ddb-8c0e-b26726edfe6c.png)


Start up msfconsole and use the metasploit exploit.

![image](https://user-images.githubusercontent.com/93418272/178387227-4fb2bb22-afc6-44c0-8fcb-f8cf972126e7.png)


Use the Microsoft IIS WebDav ScStoragePathFromUrl Overflow module.

![image](https://user-images.githubusercontent.com/93418272/178387276-0d48ed22-e8e0-4a78-aeb7-3f9c61db989a.png)


Set the TARGETURI option to /_vti_bin that was found on the dirb scan. And set the other necessary options and run the exploit.

![image](https://user-images.githubusercontent.com/93418272/178387293-79f914d0-c77a-4293-9370-9bd3e656ac32.png)


Get a shell and find the flags in the Documents and Settings folder.

![image](https://user-images.githubusercontent.com/93418272/178387315-0bd66186-046d-42b2-b12c-4fe0e048139d.png)
