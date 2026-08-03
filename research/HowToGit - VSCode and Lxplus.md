Keeping Track of Changes in Code

# GitLab
 https://indico.global/event/642/contributions/16015/attachments/5077/8128/Week%202%20-%20lxplus%20and%20git%20-%20slides.pdf
 
 Two main git services - GitHub and GitLab

CERN has its own implementation of [GitLab](https://gitlab.cern.ch/)
`https://gitlab.cern.ch/<username>`

## shh authentication 
- It is useful to provide an [shh key](https://gitlab.cern.ch/help/user/ssh.md) to link your local machine with your account - often the simplest method
- Generate ssh key pair 
```bash
ssh-keygen -t rsa -b 2048
```
Enter passphrase or leave blank (passphrase will be needed each time you use key)
```shell
# Public key: 
~/.ssh/id_rsa.pub
cat ~/.ssh/id_rsa.pub | pbcopy # to copy to clipboard
```
## Configure git
- `git config --list`
- `git config --global user.name "Your Name"`
- `git config --global user.email "your.name@cern.ch"`
- `git config --global core.editor vim`
## Create a new project
 Use GitLab interactive session

- This is just one of several ways to create a git project
- Click on “New project/repository”
- Create blank project
- Pick a descriptive project name
- Use your username as namespace
-  Set visibility to Internal
- Create project with README

## Basic git commands
```shell
git clone ssh://git@gitlab.cern.ch:7999/idwoesth/myproject.git
```
This will create a new directory, which is your local repository
- make changes locally (add, delete, edit files)
- `git status` - see the status of uncommited changes
- `git add <filename(s)>` - stage file(s) ti be committed
- `git commit` - commit changes to your local repository 
- `git push -u origin master`-sync local changes to repository
- `git pull` - sync remote changes to local repository