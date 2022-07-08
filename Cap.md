Run a nmap scan to find for open ports

![image](https://user-images.githubusercontent.com/93418272/178009120-4b292bc0-bee9-4187-bf8a-19c508dc005a.png)


Head to the web server and a security tool is found. 

![image](https://user-images.githubusercontent.com/93418272/178009152-c412c8ad-648b-4670-b79d-d47f038e593b.png)

Pcap files can be downloaded 

![image](https://user-images.githubusercontent.com/93418272/178009182-1ea063ba-9a2f-4395-9f49-1a18d12241ea.png)

![image](https://user-images.githubusercontent.com/93418272/178009207-ceda3cfb-f47d-44fe-b2fd-361ed21892b2.png)

Follow the TCP stream on that particular pcap file but no clues available.

![image](https://user-images.githubusercontent.com/93418272/178009226-a3a3d083-efe3-48d1-b21c-f9b11083a4ea.png)


In the url type in 0 to get another pcap file.

![image](https://user-images.githubusercontent.com/93418272/178009260-07bdd13a-517e-4528-a0ca-898314976868.png)


Follow the tcp stream and user credentials are found in plain text.

![image](https://user-images.githubusercontent.com/93418272/178009311-15a129c0-7cff-4cd2-aa74-e037926d1e55.png)


Login via ssh and the user.txt is found.

![image](https://user-images.githubusercontent.com/93418272/178009549-b992be7f-5568-4d87-9d33-454b471ccdcc.png)


Python can be used to get root access.

![image](https://user-images.githubusercontent.com/93418272/178009588-7eb60ba9-dd52-4023-9979-373e58c36a6f.png)


Start python and setuid to o and root access is gained.

![image](https://user-images.githubusercontent.com/93418272/178009609-fa556926-3e9b-4a93-91f0-3bbe16070923.png)
