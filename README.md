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



















