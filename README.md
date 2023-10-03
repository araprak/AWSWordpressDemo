# A Cloud-Based WordPress Blog: A Step-by-Step Tutorial

Project: Creating a WordPress blog page accessible all over the globe using AWS EC2, Elastic IP, Apache2, and MySQL
Link to access the website:  http://13.234.39.173/wordpress/

Overview:

This project demonstrates how to create a WordPress blog page that is accessible all over the globe using AWS EC2, Elastic IP, Apache2, and MySQL. The blog page is currently accessible only on an HTTP protocol and not on an HTTPS protocol, but further testing will be done to make it operational on the HTTPS protocol and to add a personal domain name to it.

Steps:

Create an EC2 instance:
Create an EC2 instance with the virtual machine running on Ubuntu OS.
Create an Elastic IP address:
Create an Elastic IP address and associate it with the EC2 instance.
Install Apache2:
SSH to the EC2 instance and install Apache2 software.
Install MySQL:
Install MySQL server on the EC2 instance.
Create a WordPress database:
Create a new database for WordPress.
Install WordPress:
Download the latest WordPress package and unzip it.
Move the WordPress folder to the Apache document root directory.
Configure WordPress:
Launch the WordPress installation wizard and enter the necessary information.
Restart Apache:
Restart the Apache web server.
Commands:

# Install Apache2
sudo apt install apache2

# Install PHP runtime and PHP MySQL connectors
sudo apt install php libapache2-mod-php PHP-MySQL

# Install MySQL server
sudo apt install MySQL-server

# Login to MySQL server
sudo mysql -u root

# Change authentication plugin to mysql_native_password (change the password to something strong)
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'Testpassword@123';

# Create a new database user for WordPress (change the password to something strong)
CREATE USER 'wp_user'@localhost IDENTIFIED BY 'Testpassword@123';

# Create a database for WordPress
CREATE DATABASE wp;

# Grant all privileges on the database 'wp' to the newly created user
GRANT ALL PRIVILEGES ON wp.* TO 'wp_user'@localhost;

# Download WordPress
cd /tmp
wget https://wordpress.org/latest.tar.gz

# Unzip
tar -xvf latest.tar.gz

# Move the WordPress folder to the Apache document root
sudo mv wordpress/ /var/www/html

# Restart Apache
sudo systemctl restart apache2


To make the blog page operational on the HTTPS protocol and to add a personal domain name to it, you can follow these steps:

Install the Certbot tool:
sudo apt-get update
sudo apt install certbot python3-certbot-apache
Request and install an SSL certificate for your domain name:
sudo certbot --apache
Configure WordPress to use HTTPS:
Go to Settings > General.
Under the Site address, enter your domain name with the HTTPS protocol. For example, https://www.mydomain.com.
Click Save Changes.
Once you have completed these steps, your WordPress blog page will be accessible on both HTTP and HTTPS protocols.

Conclusion:

This project demonstrates how to create a WordPress blog page accessible all over the globe using AWS EC2, Elastic IP, Apache2, and MySQL. The blog page is currently accessible only on an HTTP protocol and not on an HTTPS protocol, but further testing will be done to make it operational on the HTTPS protocol and to add a personal domain name to it.
