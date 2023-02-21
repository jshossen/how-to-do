## How to install nginx, PHP, PHPMyAdmin, mysql, certbot (lets encript)


### Install nginx, php, phpmyadmin, mysql
`sudo apt-get install nginx`

`sudo apt-get install mysql-server`

`sudo apt install software-properties-common`

`sudo add-apt-repository ppa:ondrej/php`

`sudo apt update`

`sudo apt install php7.4 php7.4-fpm php7.4-mysql php7.4-curl `

`sudo apt-get install phpmyadmin`

`sudo service nginx restart`


### Configure domain and subdomain http and https
`cd /etc/nginx/sites-available/`

File 1: `jshossen.conf`
File 2: `phpmyadmin.conf`


### Create Symbol 
`cd /etc/nginx/sites-available`;
`sudo ln -s jshossen.conf /etc/nginx/sites-enabled`

