https://app.hackthebox.com/machines/Networked

Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/182989176-b2b3268a-89f9-4c41-b5a5-2986ed5f1711.png)


Homepage doesn't show much.

![image](https://user-images.githubusercontent.com/93418272/182989205-a33f2bb9-7c13-4eea-a4fc-33c6bac68a0d.png)


Run a gobuster scan to find for directories.

![image](https://user-images.githubusercontent.com/93418272/182989220-91646f69-f076-4d9e-b731-b13f95259316.png)


A place to upload files.

![image](https://user-images.githubusercontent.com/93418272/182989237-df9c1b4d-56ed-4a12-91f9-d92384fad71c.png)


Backup folder with a zipped file.

![image](https://user-images.githubusercontent.com/93418272/182989253-64fce850-989a-4a9d-b0fe-d658a5704c24.png)


Download and unzip the backup folder to get some php source codes.

![image](https://user-images.githubusercontent.com/93418272/182989274-767cd780-6373-4c47-adf1-bc934a18d76e.png)


Upload.php shows a check file function.

![image](https://user-images.githubusercontent.com/93418272/182989288-691e1a8b-2501-4e0c-9b16-f94c54a7446e.png)


lib.php shows a file_mime_type function.

![image](https://user-images.githubusercontent.com/93418272/182989302-6d887961-f004-4233-8cb3-e2456076d520.png)

![image](https://user-images.githubusercontent.com/93418272/182989318-4aab08b1-c1af-429a-909b-58137ca4b4f6.png)


Let's create a png file and inject some php code to test if the file can be uploaded.

![image](https://user-images.githubusercontent.com/93418272/182989331-aac81356-3093-46e0-87ff-c15fa36ec7ff.png)


File uploaded.

![image](https://user-images.githubusercontent.com/93418272/182989346-e2977dc7-959e-413d-ab4a-714c3dbd458e.png)

![image](https://user-images.githubusercontent.com/93418272/182989361-adb8f888-c664-41ce-a4b8-54ee743b971a.png)

![image](https://user-images.githubusercontent.com/93418272/182989373-0db66b31-6ad2-4236-9820-83dee892a2b9.png)


Lets upload another php png file with reverse shell code.

![image](https://user-images.githubusercontent.com/93418272/182989392-ceb66cf3-dbc2-4f5a-a5d3-85b175b8c6c9.png)


Access gained.

![image](https://user-images.githubusercontent.com/93418272/182989407-88995aec-41a9-4d5b-a17e-5df84e446c98.png)


Unable to get user text , so looking through the other files we can notice that the system deletes unwanted files through a cronjob and command injection can be executed.

![image](https://user-images.githubusercontent.com/93418272/182989439-ac00b328-1d84-4051-99dd-a7adae62e497.png)


Create a nc listener to another port.

![image](https://user-images.githubusercontent.com/93418272/182989455-dc1fcd68-78a9-4e94-855f-dd72ad853917.png)


After 3 mins we gain access to another user and the user.txt file can be read.

![image](https://user-images.githubusercontent.com/93418272/182989466-351e115b-0af2-40d4-b08f-fd4e660fd760.png)


Sudo -l shows us a way to gain root access.

![image](https://user-images.githubusercontent.com/93418272/182989484-17d36530-30cd-47c5-8861-b7649d8ad4a5.png)


After some googling we can run the changename.sh file with sudo and input bash at the interface name and the root access is gained.

![image](https://user-images.githubusercontent.com/93418272/182989502-e2b13675-4468-4c5b-9ce3-e2ec35810e42.png)
