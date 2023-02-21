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


### install certbot
`sudo apt-get install python3-certbot-nginx`


### Install wildcard(*) ssl for jshossen.com and *.jshossen.com
`sudo certbot certonly --manual -d *.jshossen.com -d jshossen.com --agree-tos --no-bootstrap --manual-public-ip-logging-ok --preferred-challenges dns-01 --server https://acme-v02.api.letsencrypt.org/directory`


### Link cert and key file inside jshossen.conf
`ssl_certificate         /etc/letsencrypt/live/jshossen.com/fullchain.pem;`
`ssl_certificate_key     /etc/letsencrypt/live/jshossen.com/privkey.pem;`

