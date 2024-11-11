# Login to the VPS server 

- Get Access to Remote Server via SSH


## Access Your VPS
- After the VPS is set up, you'll receive the IP address and login details.
- Use SSH to connect to your VPS from your local machine. Open a terminal and run:
- 
- Copy code bash

`ssh username@your_vps_ip`
`Password which you have created during the VPS initialization`
- Replace username with your VPS `username` (typically/defealt user is =  root) and `your_vps_ip` with the actual IP address of your server.
- you will be loginged into your server
- if unable to connect than run this command 
- `ssh-keygen -R YOUR_VPS_IP_ADDRESS`
- it will delete your .ssh_key from your local machine from .ssh folder


- Verify that all required softwares are installed

## instulatation and updatation 
- run the following command
```sh
sudo apt update
sudo apt upgrade

```


```bash
nginx -v  
node -v
npm -v
git --version
pm2 --version
- Install Software (If required) once you have installed the software package from next setup no need to install it again
```


# Update the package list and install the necessary packages
- run the following command

```sh

1. **install NVM** :-   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
- nvm -V 
- if it will not show the version than restart the server

2. **install Node** :-  nvm install --lts
- node --version

3. **install mongoDB for linux** :- curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \ --dearmor
                                :- echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list


#### update the data

sudo apt-get update

- **install MongoDB**  :-  sudo apt-get install -y mongodb-org

- **if require instal mongoDb by runing code** :-  npm i mongodb 


# Start MongoDB

sudo systemctl start mongod
sudo systemctl enable mongod
sudo systemctl status mongod


4. **install git**

sudo apt install git
sudo apt update
sudo apt install gh
gh auth login     - **flow the ungoing process for login authorization with github** 
git clone `url`   - ** clone the repository**

## we can clone the repo or we can directly copy the file to the server using ftp or sftp or rsync or any other method for example we can use `scp` commend to copy

scp -P PORT{defealt port is 22} /path/to/local/folder username@your_vps_ip:/path/to/remote/folder

- Replace username with your VPS `username` (typically/defealt user is =  root) and `your_vps_ip` with the actual IP address of your server.




5. **Install PM2**

npm i -g pm2
pm2 ls
pm2 start npm --name "Give_server_name" -- start     :- **this will create server for your backend. run  this cmd in Bankend folder**
pm2 logs Give_server_name   :- **this will check whether your server is running well or not is not than  **
pm2 restart Give_server_name  - **this will restart the server**


6. **Install Nginx**

- **install Nginx** :-        sudo apt-get install nginx
- **start Nginx** :-          sudo systemctl start nginx
- **enable Nginx** :-         sudo systemctl enable nginx
- **check Nginx status** :-   sudo systemctl status nginx


7. **Install pnmp**

npm i -g pnpm

- it will work like npm but it will be faster than npm

```
