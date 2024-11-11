# setup the Project file in your server

- login to remote server
- navigate to the project directory



# **Back-end**
## visit / move inside to Backend folder 
#### install the dependencies and setup .env files flow the step below
```bash
- run_command

 pnpm install / npm install

- setup .env 

 nano .env    - (nano is used for creating empty text files and cat is ueded to read the text file)
- set environment variable inside nano .env 
- save and exit nano .env 
ctrl + O             - to save the configuration 
enter 
ctrl + X             - to exit nano .env

```

# ** start the Backend **
- start the Backend server
```bash
pnpm start / npm start or with PM2 server
pm2 ls
pm2 logs Give_server_name

```


# **Front-end**
## visit / move inside to Frontend folder 
#### install the dependencies and setup .env files flow the step below

```bash
- run_command

pnpm install / npm install

- setup .env

nano .env

- set environment variable inside nano .env
- save and exit nano .env 
ctrl + O             - to save the configuration 
enter 
ctrl + X             - to exit nano .env


- if you have created constraints.js file or othe js files for connectivity for the server than setup for it same as nano .env

```


# ** start the Frontend **
- start the Frontend server
```bash

pnpm build / npm run build

#### **build and preview**
- first check the ufw status if 4173 is allowed or not. make sure 4173 / 3000 is allowed this port allow to run the build and preview webpage

sudo ufw status
sudo ufw allow 4173 / 3000
pnpm preview --host  or    npm run preview --host

- after preview is done deny the port 4173 / 3000 to prevent any unwanted access to the server
- now you can visit the webpage by visiting the ip address of the server with port 4173 / 3000

sudo ufw deny 4173 / 3000

- up to here it's done now go for the server configuration
```



