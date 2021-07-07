# Cannon

![image](https://user-images.githubusercontent.com/85458014/124807053-bfda1a00-df33-11eb-9a56-6f3e38db2dab.png)

Cannon is a post-exploitation framework fully developed in python3. Once you have access to the system, this will make your work much easier with all the functionalities that this tool possesses. You will be able to download and upload files, run pre-defined modules, harvest reverse shells, and many more. This version of Cannon mainly focuses on attacking Unix-based machines. Most of the utilities that this framework carries based on Unix-based systems. But some of the functions will still work in Windows systems as well.

# Installation

`git clone https://github.com/kavishkagihan/Cannon/cannon.git && cd cannon && chmod +x cannon`

# Setup

Once you have this installed, you can run it with this,

`./cannon `

This will start the listener on our loopback address with the default port. If you want to specify an IP address and a port, you can  specify it like this,

`./cannon 192.168.1.102 4444`

Then you can use the `help` command to see the help menu.

# Usage
