# **Configurations file for Server**
- from Dependency installation, you have installed the inginx dependencies if not than install it

- we go thruogh the configuration setup

## visit the nginx configuration folder
- flow the steps

### For **IP configuration**

- open the file in the `/etc/nginx/sites-available/` folder
- create a configuration file for your IP address 

`nano Your_IP_address.conf`

- add the following code to the file
```bash


server {
    listen 80;
    server_name Your_IP_address;
    root /root/your/build/folder/Location;

    location / {
        try_files $uri $uri // index.html;
    }
}


- save and exit nano 
ctrl + O             - to save the configuration 
enter 
ctrl + X             - to exit nano .env 

- open the file in the `/etc/nginx/sites-enable/` folder
- enable the symbolic linke for `/etc/nginx/sites-available/`  use the below code

ln -s ../sites-available/Your_IP_address.conf .

-  replace Your_IP_address.conf with your Your_IP_address.conf

sudo nginx -t   - to check the syntex
sudo systemctl restart nginx  - to restart the server

```


### For **Domain configuration**

`nano Your_Domain_Full_name.conf`

- add the following code to the file
```bash

server {
    listen 80;
    server_name Your_Domain_Full_name wwww.Your_Domain_Full_name;
    root /root/your/build/folder/Location;

    location / {
         try_files $uri $uri // index.html;
    }
}

- flow the above steps to save and enable the symbolic link and restart the server
```


### For **Backend configuration**

`nano Your_Backend_api_Full_name.conf`

- add the following code to the file
```bash

server {
        listen 80;
	server_name Your_Backend_api_Full_name www.Your_Backend_api_Full_name;

        location / {
                proxy_pass http://localhost:5003;          - # ( replace the 5003 port to your backend port )
                proxy_http_version 1.1;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $host;
                proxy_cache_bypass $http_upgrade;
        }
}




- flow the above steps to save and enable the symbolic link and restart the server
```


- **Note**: Make sure to replace `Your_Domain_Full_name` and `Your_Backend` 
- **Note** :- again visit Frontend folder and edit the fllowing in .env file
            1. rmove the localhost URL with `https://Your_Backend_api_Full_name` 
            2. save the file and rebuild the frontend file
            3. restart the server
