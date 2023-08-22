# AWSWordpressDemo

By using AWS EC2 service I was able to create a WordPress webpage article that is accessible all over the globe. Currently, the webpage can be accessed only on an HTTP protocol and not on an HTTPS protocol. Further testing would be done to make it operational on the HTTPS protocol and to add a personal domain name to it. Currently, this is the website address - http://13.234.39.173/wordpress/

The method I used to create my own WordPress blog page.

Step 1.
Created an EC2 instance with the virtual machine running on Ubuntu OS.

Step 2.
Created an Elastic IP address and associated it with the EC2 instance to ensure a static IP address is maintained instead of a dynamic address. (This is because whenever the said EC2 instance is rebooted the IPv4 and DNS address changes. Hence I used the Elastic IP address protocol.)

Step 3.
I SSH to the EC2 Instance and installed Apache2 software as it was compatible, modular and easily customizable, and had a lot of security such as SSL/TLS Certification Support with the WordPress application.

