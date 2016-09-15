# magento
Magento Community Edition 1.9.2.4

# Build required
1. Apache
2. PHP 
3. MySQL 


# Install Apache
$ sudo apt-get install apache2

$ sudo service apache2 restart


# Install PHP
$ sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql

$ sudo apt-get install php5-curl

$ sudo apt-get install php5-gd

$ sudo a2enmod rewrite


# Install MySQL
$ sudo apt-get install mysql-server


# Configuration MOD_REWRITE
$ sudo nano /etc/apache2/sites-enabled/000-default.conf

Inside that file, you will find the <VirtualHost *:80> block on line 1. Inside of that block, add the following block:

	<Directory /var/www/html>
	    Options Indexes FollowSymLinks MultiViews
	    AllowOverride All
	    Order allow,deny
	    allow from all
	</Directory>

$ sudo service apache2 restart

# Ubuntu Firewall: Apache only visible on lan
$ sudo ufw allow from 192.168.1.0/24 to any port 80

# Thank you very much..
