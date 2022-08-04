Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/182754058-95b66b0d-58b8-4204-a988-0c443d25dbb5.png)

![image](https://user-images.githubusercontent.com/93418272/182754091-f0fc32f3-7f18-4878-bb97-5c510177eef5.png)

Web server shows just an image.

Run a gobuster scan to find for directories. 

![image](https://user-images.githubusercontent.com/93418272/182754122-f0c22668-e194-451e-a0de-6dff4cb8cc46.png)

![image](https://user-images.githubusercontent.com/93418272/182754145-80894814-01ae-4ee8-99a6-9889d4d02c53.png)

![image](https://user-images.githubusercontent.com/93418272/182754155-8a2f4d24-8231-4c7b-8249-94c8f6ee26da.png)

![image](https://user-images.githubusercontent.com/93418272/182754169-41402b70-5027-43a9-b98b-8e5948099c31.png)

![image](https://user-images.githubusercontent.com/93418272/182754181-5de7a6fb-1891-4166-a8fc-e560b8b528f0.png)

![image](https://user-images.githubusercontent.com/93418272/182754189-33e5be44-30ad-433f-8367-9ef569a51585.png)

Looks like some kind of hex key.

![image](https://user-images.githubusercontent.com/93418272/182754213-2c35b7c2-8dc6-455f-920d-f277bfd4a178.png)


Use a decoder on the hex file and it is a RSA private key.

Tried using the private key to ssh into the user but needed a pass phrase. Used john to crack the hash but no password found.

From the theme of the box and the image on the webserver it seems to be a heartbleed exploit. 

Let's use nmap to check for this vulnerability.

![image](https://user-images.githubusercontent.com/93418272/182754242-7403b420-defd-4a61-aa9d-dfc8ebf4c159.png)


From the vulnerability check heartbleed (CVE-2014-0160) can be exploited with a python file.

![image](https://user-images.githubusercontent.com/93418272/182754263-808401ba-5e1a-46de-a117-f0adb8933469.png)


There are couple of heartbleed exploit scripts around. I use the following here 

Run the exploit using python2.

![image](https://user-images.githubusercontent.com/93418272/182754275-1e742fdd-4c1e-4a90-8a91-f4df0077604d.png)

A base64 code is found.

Head to the webserver decoder and decode the base64 text.

A potential passphrase is found.

![image](https://user-images.githubusercontent.com/93418272/182754320-2be32922-6c5d-45d7-ba26-ac525d00b566.png)


Login with private key and the newly found passphrase. 

heartbleedbelievethehype

On the first attempt I get an error message , use the additional flag to gain access.

![image](https://user-images.githubusercontent.com/93418272/182754350-54373e7e-e6d0-4e10-abf8-983c0c39236d.png)


The first flag is found.

![image](https://user-images.githubusercontent.com/93418272/182754362-6666a448-70f4-400f-8236-dce6213095be.png)


Use LinEnum to find for privileged escalations.

![image](https://user-images.githubusercontent.com/93418272/182754384-c5996dc1-5b3d-4323-9767-549c75dbf4e2.png)


From ps aux we can see root is running on tmux.

![image](https://user-images.githubusercontent.com/93418272/182754398-780e3494-22d0-4f76-8e70-c5ed55b566f0.png)


Run the following command to gain a root shell : tmux -S /.devs/dev_sess

![image](https://user-images.githubusercontent.com/93418272/182754418-95a2e984-4f62-4faa-bcaa-cec69ae893a6.png)
