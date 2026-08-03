---
tags:
  - status/wip
  - type/commands/shell
aliases:
---
**One tip:** memorize the machine you ssh into, and ssh to it if you wanna get back to the same processes later

You want to use lxplus for working with [[FairShip]], because it gives you the [[CERN]] computing power and all the benefits for working in a collaboration, where everyone uses lxplus and [[GitHub]]. Usually all the simulation data you are working with (or generating yourself) will be stored on CERN servers. I am no expert on all the specifics but access this data and being able to use for example [[HTcondor]] for doing heavy calculations is easy from within lxplus. EVERONE uses it and it's great (most times), so do so too. :)

[[HowToLxplus CERNbox]]

[A Quick Intro to lxplus,bash & python](https://indico.cern.ch/event/1206471/contributions/5157610/attachments/2555218/4403029/Bash-Python%20Intro%20Starterkit%202022.pdf)
## What is lxplus? 
the interactive logon service to Linux for CERN users, consisting of a cluster of public machines provided by CERNs IT department for interactive work

## How to use lxplus?
Basically just ssh int it and use it like usual linux terminal. 

This is very easy if you are on Linux yourself, but gets tricky on Windows and Mac. 
Linux is highly recommended.
- It is possible to use Linux with dual boot (every time you start your computer you can choose which system you want to use)
- It is also possible to use a Virtual Box
- You can also access lxplus via VScode ssh. 
	- this can be very efficient but there are some problems that occur:
	- lxplus uses changing machines with different adresses, while VScode ssh requires a global one. So every time the host needs to be chosen again 
	- Eduard solved this by changing the global shh adress in VS code to the adress of lxplus
	- He did that on my computer so ask him about it

## How to enter lxplus terminal 
Once you are on Linux:
- you need a stable internet connection 
- go to the terminal (contoll + \` on Mac VS code)
- type `ssh -X <your-username>@lxplus.cern.ch` - where X enables Graphics
	- If you work from VS code you can install the extention [ROOT File Viewer](https://marketplace.visualstudio.com/items?itemName=albertopdrf.root-file-viewer) to look at Graphes in ROOT - I think that works instead of -X
	- once set up in VS code you can just klick on the symbol in the left lower corner 
- You will be ask for your password (type and enter, it might not be displayed)
- You should see a welcome massage and some info from lxplus
- You can now use lxplus like a linux controlled from terminal - [[useful linux commands]]
- There are also some [[useful git commands]] you will need

[[bash introduction]]
