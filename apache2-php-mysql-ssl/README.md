## How to install apache2, PHP, PHPMyAdmin, mysql, certbot (lets encript)


### Install apache, php, phpmyadmin, mysql
`sudo apt-get install apache2`

`sudo apt-get install mysql-server`

`sudo apt install software-properties-common`

`sudo add-apt-repository ppa:ondrej/php`

`sudo apt update`

`sudo apt install php7.3`

`sudo apt install php-pear php7.3-curl php7.3-dev php7.3-gd php7.3-mbstring php7.3-zip php7.3-mysql php7.3-xml php7.3-fpm libapache2-mod-php7.3 php7.3-imagick php7.3-recode php7.3-tidy php7.3-xmlrpc php7.3-intl`

`sudo apt-get install phpmyadmin`

`sudo service apache2 restart`


### Configure domain and subdomain http and https
`cd /etc/apache2/sites-available/`

File 1: `000-default.conf`
File 2: `jshossen.conf`
File 3: `subdomain-jshossen.conf`

### Add both files to apache conf
`sudo a2ensite jshossen.conf`
`sudo a2ensite subdomain-jshossen.conf`

### Remove file (if needed)
`sudo a2dissite “file name”`


### Installl certbot

`sudo apt-get update`
`sudo apt-get install software-properties-common`
`sudo add-apt-repository ppa:certbot/certbot`
`sudo apt-get update`
`sudo apt-get install python-certbot-apache`

`sudo certbot certonly --manual -d *.jshossen.com -d jshossen.com --agree-tos --no-bootstrap --manual-public-ip-logging-ok --preferred-challenges dns-01 --server https://acme-v02.api.letsencrypt.org/directory`

### Renew: 
`sudo certbot --apache -d subdomain.jshossen.com -d jshossen.com`

### Enable ssl
`sudo a2enmod ssl`

### Install composer

`sudo apt-get update`

`sudo apt-get install curl php-cli php-mbstring git unzip`

`cd ~`

`curl -sS https://getcomposer.org/installer -o composer-setup.php`

`php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"`

`sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer`

`composer`

### Change php version
`sudo update-alternatives --set php /usr/bin/php7.3`

