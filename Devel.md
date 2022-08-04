https://app.hackthebox.com/machines/Devel

Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/182834791-2790ce92-0961-44b1-8c01-6c8a5c8e8d11.png)


Webserver shows the IIS7 service.

![image](https://user-images.githubusercontent.com/93418272/182834814-2c46f28b-67d5-4c38-bdf0-810cd3502842.png)


Login to the FTP server via anonymous

![image](https://user-images.githubusercontent.com/93418272/182834831-fcf2ebf3-1179-4766-9cdb-ff720e59e966.png)

It is a asps webserver , we can craft a reverse shell and put it inside the server.

Use msfvenom to create a payload.

![image](https://user-images.githubusercontent.com/93418272/182834853-8c1220da-025f-4850-ae38-af5ae944fbe6.png)

Upload the payload via the FTP server.

![image](https://user-images.githubusercontent.com/93418272/182834882-c586bb18-09c5-41c5-a314-b42fdf51334f.png)

Start a netcat listener and reload the reverse shell in the browser.

![image](https://user-images.githubusercontent.com/93418272/182834929-e2061688-f8af-4647-9a3f-fc35b15fedae.png)

We can search an exploit for wndows 6.1.7600

![image](https://user-images.githubusercontent.com/93418272/182834979-c7b1690f-0501-48b3-884e-f147742ae4a4.png)

Download the exploit 

![image](https://user-images.githubusercontent.com/93418272/182835021-b2bf2bd1-d82a-4091-a8e1-471c038a2e53.png)

Upload it to the FTP server

![image](https://user-images.githubusercontent.com/93418272/182835054-b7cfd387-61c5-45bf-a0b7-bb6a4202f8f2.png)

Move to the inetpub\wwwroot directory to find the upload.

![image](https://user-images.githubusercontent.com/93418272/182835103-2b40dc78-19c9-4f6d-9e77-06d8fc3fd223.png)


Run the exploit and root is gained.

![image](https://user-images.githubusercontent.com/93418272/182835129-0edb15fe-dbc7-4470-942b-6e61859820b1.png)

![image](https://user-images.githubusercontent.com/93418272/182835153-589d72b0-cec3-47e2-be54-0e33ef75e5d4.png)

![image](https://user-images.githubusercontent.com/93418272/182835169-d611eb33-b516-4a61-8a34-a681b397d038.png)

