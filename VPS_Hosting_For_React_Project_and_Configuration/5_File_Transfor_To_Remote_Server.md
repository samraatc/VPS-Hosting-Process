# Project File Transfer

- there is many different ways to transfer files but we talk about 2 different ways to transfer
1. git clone
2. scp checkout


## Git clone

- git clone is a command that allows you to download a copy of a repository from your git to your a remote server

- i have given cammand in `4_Dependency_install.md` 
- again here

```bash
- flow the step of cloning a repository
- **install git** - if installed then directly go with `git clone {repo url}` cmd

sudo apt install git
sudo apt update
sudo apt install gh
gh auth login     - **flow the ungoing process for login authorization with github** 
git clone `url`   - ** clone the repository**

```


## scp checkout
- scp is a command that allows you to securely copy files between two locations on a network 

- To copy a file from your local machine to the remote server, use this code

```bash

scp -P PORT{defealt port is 22} /path/to/local/folder username@your_vps_ip:/path/to/remote/folder

- Replace username with your VPS `username` (typically/defealt user is =  root) and `your_vps_ip` with the actual IP address of your server/vps ip.


```


