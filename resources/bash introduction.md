---
tags:
  - topic/coding
aliases:
  - shell
  - terminal
---
 For further information on bash check the documentation: https://devdocs.io/bash/ 
## Bash Introduction
#type/commands/shell
`pwd`: Shows the current working directory path †
`ls`: list files/directories: 
	`ls -a`: for hidden directories
	`ls -l`: for extra details
	`ls <path to dir`> to peek at a specific directory 
`touch filename` create a new file
`mkdir dir` create a directory
`cp source destination` copy 
`mv source destination` move
`rm -d` removing a directory
`rm -r` recursive, remove directory and its contents
`command --help` 

`echo "prints the following statement to the terminal"`
`echo "We are storing ${1} in 'myVariable'` refers to the first variable in that script
`export myVariable=$1` Creates a new environment variable
`echo "myVariable is ${myVariable}` Now uses it. $name tells bash to look for the variable "name"

Exercise! Have a go playing around with this script to
get some practise! Idea: What does $0 do? [[PhD To Dos]]
## Editing Files - a million ways
- Terminal Text Editors: [[vim]], [[nano]]
- [[Visual Studio Code]]


- bash scripts can be used to create variables within other environments: 
	- Instead use `$ source testScript.sh something`
	- now `echo $myVariable` is available

# .bashrc: 
Located in your $HOME/.bashrc is a very convenient file for storing your favourite environment variables and commands.

For mac it can also be zsh see [[Wavecatcher analysis modification for apple]]

Every time you login to lxplus $ source .bashrc runs automatically!
e.g I have export WORK=/afs/cern.ch/work/d/dathomps/ in mine!
