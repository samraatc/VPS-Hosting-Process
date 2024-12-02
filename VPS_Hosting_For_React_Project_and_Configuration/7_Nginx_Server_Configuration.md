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
-  visit the frontend build folder and and type `pwd` to know the present directory and copy the full path
```bash



server {
    listen 80;
    server_name Your_IP_address;
    root /root/your/build/folder/Location;

    location / {
        try_files $uri $uri // index.html;
    }
}
```


> - save and exit nano

> - ctrl + O             # to save the configuration 
> - enter 
> - ctrl + X             # to exit nano .env
> 
> 
> - open the file in the `/etc/nginx/sites-enable/` folder
> - enable the symbolic linke for `/etc/nginx/sites-available/`  use the below code


```bash
ln -s ../sites-available/Your_IP_address.conf .  

```

> -  replace Your_IP_address.conf with your Your_IP_address.conf

```bash
sudo nginx -t                    # to check the syntex
sudo systemctl restart nginx     # to restart the server

```


### For **Domain configuration**

> `nano Your_Domain_Full_name.conf`
> 
> - add the following code to the file
> - visit the frontend build folder and and type `pwd` to know the present directory and copy the full path

```bash



server {
    listen 80;
    server_name Your_Domain_Full_name wwww.Your_Domain_Full_name;
    root /root/your/build/folder/Location;

    location / {
         try_files $uri $uri // index.html;
    }
}


```
- flow the above steps to save and enable the symbolic link and restart the server

  


### For **Backend configuration**

> `nano Your_Backend_api_Full_name.conf`
> 
> - add the following code to the file

```bash


server {
        listen 80;
	server_name Your_Backend_api_Full_name www.Your_Backend_api_Full_name;

        location / {
                proxy_pass http://localhost:5003;           # ( replace the 5003 port to your backend port )
                proxy_http_version 1.1;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $host;
                proxy_cache_bypass $http_upgrade;
        }
}

```
> - flow the above steps to save and enable the symbolic link and restart the server
> 
> 
> 
> - **Note**: Make sure to replace `Your_Domain_Full_name` and `Your_Backend` 
> - **Note** :- again visit Frontend folder and edit the fllowing in .env file
>    1. rmove the localhost URL with `https://Your_Backend_api_Full_name` 
>    2. save the file and rebuild the frontend file
>    3. restart the server
> 
- **Note** :- some time even after correct configuration project does not reflect on domain so we need to add ssl certificate. after adding this the project satart to render on the domain

   
# SSL Setup
- We are going to use Let’s Encrypt SSL certificate using certbot. To install certbot:

### install python 

```py
sudo apt-get install certbot python3-certbot-nginx

```

####  To install certificate to your domain you can use this command:

sudo certbot --nginx -d mywebsite.com -d www.mywebsite.com (add this if you have created subdomain www :- `-d www.mywebsite.com`)

> - you can also use "sudo certbot --nginx -d mywebsite.com" but since we have "www"
> - too we are passing another argument with another website.
> - When you do it for first time, it will ask for email, enter any email.
> - Then it will tell to agree to conditions or whatever, choose "Y"
> - At last, it will tell if you want to share your email, choose "n"
> 
> -  Now, let's do for our api one

```bash

sudo certbot --nginx -d api.mywebsite.com -d www.api.mywebsite.com
```

> - add the subdomain or domain to which you want to add ssl certificate
> - SSL is successfully installed on your website

### **Note** :- After installing ssl on your api, you would need to change api url from client/frontend because we had used “http” at that time. So, go to your client/frontend, update your API URL with https and build the project.

```
