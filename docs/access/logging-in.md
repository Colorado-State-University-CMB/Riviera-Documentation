# Logging In

Research Computing offers a variety of resources for researchers to use in their own projects. To get started with Research Computing resources you need the following: 

- [A Research Computing account](https://www.research.colostate.edu/dsri/hpc-riviera/)
- [The PuTTY application](https://www.putty.org/) (if you are a Windows user)  

Users accessing RC's resources will be connected to a login node. A login node is a outward facing node within the Research Computing environment that users can connect to from their local machines. Once on a login node, users can perform a limited number of tasks:

+ Edit files
+ Transfer Data
+ Running Jobs
+ Access storage resources  

> **Note:** the [login node policy](../additional-resources/policies.md#login-nodes) states that login nodes should not be used for resource-intensive tasks such as running code. For all other tasks, users should run batch jobs, interactive jobs, or use the compile nodes. 
---
## Getting an account

Although Research Computing resources are free and available to the CSU research community, they are also managed resources with large value and high demand. Therefore, Research Computing mandates that each user obtain a Research Computing account. 

A Research Computing account can be secured quickly and easily [by filling out the form 
here](https://www.research.colostate.edu/dsri/hpc-riviera/).
  
## Logging in from a Windows Machine

Logging in from a Windows machine requires the additional step of [installing the PuTTY ssh client](https://www.putty.org/) onto your local machine. This application allows users to connect to remote servers with the ssh protocol. Note that there are other ssh clients that allow Windows machines to connect to remote ssh servers; Research Computing recommends PuTTY for reliability and simplicity.

1. Open the PuTTY application on your computer
    * Under “Host Name (or IP address)”, enter `login.riviera.colostate.edu`. Select “SSH” as the connection type. Click on “Open”.
2. Enter your Identikey in response to the “login as” prompt
3. When prompted to enter your password:
    * Note that as a security feature, PuTTY does not display any text while you type your password
## Logging in from a Mac

Logging in with a Mac requires no extra installation on your local machine. Simply utilize the terminal application that is pre-installed with your operating system to access Research Computing resources. 

1. Under “File”, open a new finder window. Navigate to the “Applications” folder, then the “Utilities” folder. Open a terminal window and type `ssh username@riviera.colostate.edu`, where `username` is your assigned username. Press enter.
2. Enter your password:
	- Enter the password that was assigned by DSRI                
	- How to change your password

## Logging in from Linux

Much like with Macs, Linux machines require no additional setup to access Research Computing resources. Simply utilize the your Linux terminal to access Research Computing resources. 

1. Open a terminal window from your application menu and type: `ssh username@riviera.colostate.edu`, where `username` is your research computing username.

2. Enter your password:
	- Enter the password that was assigned by DSRI                
	- How to change your password

## SSH host keys

The first time you log into a login node you will be asked to verify the host key. You can refer to the keys published here to confirm that you are connecting to a valid login node.

Note that each login node may support more than one type of key, but only one is used (or displayed) by your client at any given time.