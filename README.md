# Cannon

Cannon is a post-exploitation framework fully developed in python3. Once you have access to the system, this will make your work much easier with all the functionalities that this tool possesses. You will be able to download and upload files, run pre-defined modules, harvest reverse shells, and many more. This version of Cannon mainly focuses on attacking Unix-based machines. Most of the utilities that this framework carries based on Unix-based systems. But some of the functions will still work in Windows systems as well.

# Installation

`git clone https://github.com/kavishkagihan/Cannon/cannon.git && cd cannon && chmod +x cannon`

# Setup

Once you have this installed, you can run it.

`./cannon `

This will start the listener on our loopback address with the default port. If you want to use a different IP and a port you can also specify them.

`./cannon 192.168.1.102 4444`

Then you can use the `help` command to see the help menu.

![image](https://user-images.githubusercontent.com/85458014/124820162-7eea0180-df43-11eb-8e8f-ceac1a494a09.png)


# Usage

1.Creating the payload file.

After you run cannon, you can create a payload file, which conains the payload to be executed in the victim machine. You have to specify the port which you are listening on. 

`create 4444`

Payload will be saved in a file with the name of the 'SHELL_FILE' variable (defualt is cannon.shell)
![image](https://user-images.githubusercontent.com/85458014/124819453-a7bdc700-df42-11eb-9158-a37c2c8b4638.png)



2. Executing the payload

Then you can simply execute the shell on the victim machine

`python3 cannon.shell`


3. Cheking the connections

Once you have executed the payload, you can check if you have got the connection back.

`list`

![image](https://user-images.githubusercontent.com/85458014/124819508-b7d5a680-df42-11eb-8ea6-106123b5b64e.png)


4. Interate with a connected host

You can interact with a connected host with the 'connect' command.The hosts number should be given as an argument. You can check the number of the host with 'list'

`connect 1`


5. Disconnect a host

You can simply disconnect an unwanted host with the 'disconnect'  command.The hosts number should be given as an argument.

`disconnect 1`

![image](https://user-images.githubusercontent.com/85458014/124819595-cf149400-df42-11eb-8def-ebb585a395fa.png)


6. Start another listener

You also can bind another listeners while listening from this and get connections through that as well. The port to start the listener on should be given as an argument.

`bind 9002`

![image](https://user-images.githubusercontent.com/85458014/124819627-db005600-df42-11eb-9cca-36759508af4e.png)


7. Kill an active listener

When you want to stop an active listener you can use the 'kill' command. As an argument, the port of the listener should be specified.

`kill 9002`

![image](https://user-images.githubusercontent.com/85458014/124819669-e6ec1800-df42-11eb-80c8-93a97573abe9.png)


8. Check the statistics

With the 'status' command you can list the current status such as the Internet status, Listeners IP and PORT, number of listeners and the number of hosts connected.

`status`

![image](https://user-images.githubusercontent.com/85458014/124819922-3a5e6600-df43-11eb-82f8-4f64cf31d670.png)

9. Shell access to the local machine

While you are on the cannon framework, you can execute commands on your machine. When you want to go back to Cannon you can exit the shell with 'exit'

`shell`

![image](https://user-images.githubusercontent.com/85458014/124821076-a55c6c80-df44-11eb-8c1f-557148ea17ba.png)


10. Exit Cannon

You can simply exit this with the 'exit' command.

`exit`

Also if you are comfortable with using keyborad shortcuts, you can use the Control key and the EXIT_KEY (default is 'j')  to exit as well. You change change it to your preference. 


![image](https://user-images.githubusercontent.com/85458014/124821538-392e3880-df45-11eb-9230-ef781944f3b7.png)

# Interacting with meterpreter instances

After you connect to a host (with the 'connect' command) you can do certian things which will help you further with the exploitation process. You can use the `help` command to view the help menu.

![image](https://user-images.githubusercontent.com/85458014/124867430-7b329b00-df94-11eb-958b-cf37aa929e65.png)

1. Upload files

You can upload files with the 'upload' command. This takes two arguments. First one being the source file that you want to upload. And then the destination path for the file to be uploaded. (This version of Cannon doesn't support uploading or downloading binary files. That feature will be added soon)

`upload example_file /tmp/uploaded_file`

![image](https://user-images.githubusercontent.com/85458014/124867749-0c097680-df95-11eb-8b76-c1490f9e127c.png)


You can clarify that by looking at the uploaded file.

![image](https://user-images.githubusercontent.com/85458014/124867820-29d6db80-df95-11eb-8290-bd74cdbe8892.png)


2. Download files

You can download files as well, This also takes two arguments, the path of file you want to download and the destination path to the file to be saved.

`download /tmp/uploaded_file downloaded_file`

![image](https://user-images.githubusercontent.com/85458014/124868243-de70fd00-df95-11eb-88b5-ff0295358be6.png)

Again, you can clarify it by looking at the downloaded file.

![image](https://user-images.githubusercontent.com/85458014/124868317-f9437180-df95-11eb-8022-1a4ca7a92172.png)


3. Execute commands on the victim machine

One of the useful features of this tool is that you can gain shell access to the victim machine.

`channel`

![image](https://user-images.githubusercontent.com/85458014/124915078-7dfab380-dfc7-11eb-9877-d8c2451aaae3.png)

Depending on the access you have it will show wheather you have user access or root access in the system.

![image](https://user-images.githubusercontent.com/85458014/124916053-9d461080-dfc8-11eb-8301-60f21512e2a6.png)

(This is not a tty shell, so you won't be able to run any interactive commands such as sudo)

4. Basic information about the system

With the 'info' command you can get some basic information that may be helpful. 

`info -s` to get system information

![image](https://user-images.githubusercontent.com/85458014/124915636-2577e600-dfc8-11eb-9122-cda5fe5d8caf.png)


`info -m` to get memory information

![image](https://user-images.githubusercontent.com/85458014/124915714-3c1e3d00-dfc8-11eb-9f35-0719d034838a.png)


`info -a` to get all of them at once

![image](https://user-images.githubusercontent.com/85458014/124915764-4b04ef80-dfc8-11eb-9e42-5e320e58d67e.png)


5. Harvesting reverse shells

Probably the bst and the most useful feature of this tool is that you can get a reverse shell back to you with the 'revshell' command. This takes inly one argument bing the port that you want to get the reverse shell to.

`revshell 8899`

![image](https://user-images.githubusercontent.com/85458014/124917220-ef3b6600-dfc9-11eb-8af5-431c0202df36.png)

You have to start a listener in the port you specify. 

![image](https://user-images.githubusercontent.com/85458014/124917569-5e18bf00-dfca-11eb-96df-00ba5a106f91.png)

This is where the real power of this framework comes in. Imagine you are on a very unstable box and your reverse shell dies constantly. With this you just have to run this and you will have a shell back for you in no time.












