Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/178129040-5b4617c5-9269-4013-8f09-88d5f6778b47.png)


Google the IIS version and the common exploit can be found.

![image](https://user-images.githubusercontent.com/93418272/178129043-8d260ed5-389f-44e2-9d01-e696a20d7022.png)


Web server is under construction but uses the IIS framework.

![image](https://user-images.githubusercontent.com/93418272/178129045-58b913df-c22a-4a80-9261-9428a0d76aef.png)


Start up msfconsole to find for exploits.

![image](https://user-images.githubusercontent.com/93418272/178129048-2e6bce61-38e8-4cea-91c0-767e0b98b8dd.png)


use exploit number 2

Set up the necessary options and run the exploit.

![image](https://user-images.githubusercontent.com/93418272/178129052-330ccadd-9461-4f18-bc74-d05da53c4326.png)


Migrate to the wmiprvse.exe process

![image](https://user-images.githubusercontent.com/93418272/178129056-a9a961b7-4580-4012-b809-8d3a97c1066d.png)

Cant get the full access.

![image](https://user-images.githubusercontent.com/93418272/178129068-32a16e75-d0c4-43bd-a833-20abe9b75979.png)

background the session and search for a local exploit.

exploit/windows/local/ms14_070_tcpip_ioctl is a local exploit we can use.

![image](https://user-images.githubusercontent.com/93418272/178129076-b3874caa-6be8-44fd-8e38-f60973cf0ad0.png)

Run the exploit.

![image](https://user-images.githubusercontent.com/93418272/178129081-0ef5ca93-4181-4124-8ab8-4dc1f9623c9d.png)

Head to Lakis user and get the user flag.

![image](https://user-images.githubusercontent.com/93418272/178129086-e9037122-d3e5-4495-89de-dfe64c9f851a.png)

![image](https://user-images.githubusercontent.com/93418272/178129091-b0dbb880-b0ad-4632-9edb-9fe3807f7a14.png)


Head to the Administrator folder to get the root flag.

![image](https://user-images.githubusercontent.com/93418272/178129092-c9a88444-fdc5-481d-9c31-8635eaab3f7a.png)

![image](https://user-images.githubusercontent.com/93418272/178129096-a3353ed0-9455-4933-ad83-a643adfe9c3f.png)

