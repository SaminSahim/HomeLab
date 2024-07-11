# HomeLab

This README documents the start of a Home Lab to learn more and implement concepts about virtualization, Active Directory, and Networking.

## Virtualization and Setup

For this Home Lab, I will be using VirtualBox (https://www.virtualbox.org/wiki/Downloads). I downloaded the Windows 7.0.18 version and the Oracle VM Virtual Box Extension Pack.
We will also need a Windows Server ISO file and a Windows Enterprise ISO file to run on our virtual machines/servers. 

Links: 

https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022

https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise

## VirtualBox

After setting up VirtualBox, we can create our first user by clicking new. Tune the processor and RAM allocation best suited to your computer. 

Next, we can set up our Domain Controller. Simply put, a domain controller is a server that is responsible for handling authentication requests and authorization of domain resources.
Domain controllers are used in conjunction with an Identity Provider such as Active Directory to manage all of your users and domain resources (workstations, servers, files, accounts, etc.)

After clicking New again in VirtualBox, we create a new machine while making sure to change the version to "Other Windows (64-bit)" since we are going to run Windows Server on it.

Before moving on, we have to change the network adapter settings on our client to an "Internal Network." For our DC (Domain Controller), we have to enable to second network adapter to an "Internal Network" while keeping the first adapter on NAT.

After all of that, we should have something that looks like this: 
![image](https://github.com/SaminSahim/HomeLab/assets/85653393/89308a9d-0eb1-44f7-8bc5-6f6b7048443d)

## Domain Controller

We can boot up our domain controller by double-clicking it and using the 2022 server ISO we downloaded previously. 
Move forward with the installation till you get to the Microsoft Server Operating System Setup where you will piece the Standard Evaluation with the Desktop Experience Version.
Custom install the Server only and wait till it finishes setting up. Set up a password that you will remember. It will tell you to hit Ctrl-Alt-Delete so go to the top of VirtualBox and click input > keyboard > insert ctrl-alt-delete.

After booting, you will see the Server Manager pop-up:
![image](https://github.com/SaminSahim/HomeLab/assets/85653393/c1a1463a-93aa-4fb2-8232-24a5491c160e)

Before moving on, we will make a few changes to the Domain Controller. Go into your network settings and find the two network adapters that we configured at the beginning. 
Find the one that is connected to your home network and change it's name to something that you will remember. Make sure to not fiddle with any network settings on this adapter. Go into the second adapter and click Properties. Here you will make the following changes to the Internet Protocol Version 4 (TCP/IPv4) Properties:
![image](https://github.com/SaminSahim/HomeLab/assets/85653393/a69e26ba-6140-4419-9d93-3049a75f6e24)
