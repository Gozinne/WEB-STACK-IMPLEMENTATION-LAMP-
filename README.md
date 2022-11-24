# WEB STACK IMPLEMENTATION (LAMP STACK)
</a>

![Contributors](https://img.shields.io/github/contributors/Gozinne/Project-1?style=plastic)
![Forks](https://img.shields.io/github/forks/Gozinne/Project-1)
![Stars](https://img.shields.io/github/stars/Gozinne/Project-1)
![Licence](https://img.shields.io/github/license/Gozinne/Project-1)
![Issues](https://img.shields.io/github/issues/Gozinne/Project-1)

## Setting up a LAMP stack on Ubuntu

### LAMP stack overview

The LAMP stack refers to a collection of technologies that may be used to provide dynamic web applications and webpages. 
LAMP (Linux, Apache, MySQL, and PHP) is an abbreviation. 
The notion refers to a server environment that includes a Linux operating system (Ubuntu), an Apache web server, a MySQL (or MariaDB) database server, and the PHP programming language (or Python).

### Requirements

The following items are required to begin and complete this project.
* An account and are logged into the AWS console.
* Open an AWS EC2 instance.
* Run the EC2 instance on Ubuntu and set the network security to: SSH,Port:22; HTTP,Port:80.
* Connect VScode or MobaXterm to the EC2 instance and launch a new terminal.

***
<img
  src="https://user-images.githubusercontent.com/80969889/203666926-8e0ea8f1-174d-495e-9d6f-97559d85ec52.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">

## Installing Apache and Updating the Firewall

[Apache HTTP Server](https://httpd.apache.org/) is the most widely used web server software. 
The Apache Software Foundation develops and maintains Apache, which is free open-source software that is fast, dependable, and secure. 
It may be significantly customised using extensions and modules to meet the needs of a wide range of circumstances. 
Apache saves virtual host configuration files. All accessible configuration files may be found in the [directory](/etc/apache2/sites-available/).

Install Apache using Ubuntu’s package manager ‘apt’:

#Update a list of packages in package manager
```
sudo apt update
```
#Run apache2 package installation
```
sudo apt install apache2
```
#To verify that apache2 is running as a Service in our OS, use following command
```
sudo systemctl status apache2
```
#Then access it locally in your Ubuntu shell:
```
curl http://<localhost>:80
```
If everything is green and operating, you have done everything correctly - you have just launched your own Cloud Web Server!

***
<img
  src="https://user-images.githubusercontent.com/80969889/203670715-b84728f2-2f12-4b58-9937-06b2ccd2f64f.gif"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
  
## Installing MySQL

[MySQL](https://www.mysql.com/) is an open-source database management system that is typically included in the LAMP stack. 
It follows the relational paradigm and manages its data via Structured Query Language (SQL).
By installing it, users will have a functional relational database on which to create a website or application.

#Again, use ‘apt’ to acquire and install this software:
```
$ sudo apt install mysql-server
```
#When asked, type **Y** and then **ENTER** to confirm installation.
***
#When the installation is complete, open the MySQL console by typing:
```
$ sudo mysql
```
This command will connect to the MySQL server as the administrator database user root, as implied by the use of sudo. You should get something like this:

***
<img
  src="https://user-images.githubusercontent.com/80969889/203673740-55a08f71-44a6-4429-a734-d45577e4f0d0.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
  ***

It is highly advised that you execute the security script that comes with MySQL. 
This script will prevent access to your database system by eliminating various dangerous default settings.
***
#Before running the script, you will provide a password for the root user:
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY <'PassWord.1'>;
```
Exit **mysql>** by typing "exit".
***
#Start the interactive script by running:
```
$ sudo mysql_secure_installation
```
This prompts you to configure the **VALIDATE PASSWORD PLUGIN**.
However, it is safe to leave validation turned off.
Answer **Y** for yes, or **any other letter** to proceed without enabling.
After the above you will recieve another prompt;**Yes**, press y|Y; for **No**, press any alternative key:
If you answer "yes," you will be prompted to choose a degree of password validation. 
Remember that if you pick 2 for the toughest level, you will receive problems when attempting to establish any password that does not include digits, upper and lowercase letters, and special characters, or is based on popular dictionary terms, such as PassWord.1.

***
<img
  src="https://user-images.githubusercontent.com/80969889/203675681-ebb5ea93-9c77-4b6a-a76f-4fa552771537.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
***

Whether or not the VALIDATE PASSWORD PLUGIN is enabled, your server will prompt you to enter and confirm a password for the MySQL root user. This differs from the system root. 
As an added precaution, if one has been set, you should create a strong password.
Whether password validation was enabled or not, your server will display the password strength for the root password you just typed and ask whether you wish to proceed.
At each prompt, enter **Y** and then **ENTER** to answer the remaining questions.
#To test, log in to the MySQL console as follows:
```
mysql -p sudo
```

***
<img
  src="https://user-images.githubusercontent.com/80969889/203678137-99d1222c-63ba-4b89-912c-63c02a8763e0.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
***

## Installing PHP
### What is PHP
[PHP](https://devdocs.io/php/) is a popular open source programming language that runs on the server and returns plain HTML to the browser. PHP files, which have the extension ".php," can include text, HTML, CSS, JavaScript, and PHP code. PHP has the ability to produce dynamic page content.
### Why PHP?
* It is free, simple to learn, and extremely powerful on the server side.
* It is available on a wide range of platforms.
* It is compatible with almost every contemporary server.
* It works with a wide range of databases.
Along with the php package, php-mysql and libapache2-mod-php will be required.
***
#Run the following command to install all three packages at once:
```
sudo apt install php libapache2-mod-php php-mysql
```
#Execute the following command to verify your PHP version:
```
php -v
```
LAMP stack is now fully installed and working.

***
<img
  src="https://user-images.githubusercontent.com/80969889/203685027-04aa1e56-f872-43ea-a381-6140ec5e68eb.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
 ***
 <img
  src="https://user-images.githubusercontent.com/80969889/203685102-51ccc23d-aa17-4459-87fc-98d44ac36b6b.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px"> 
***
 <img
  src="https://user-images.githubusercontent.com/80969889/203688419-dce92512-5f4a-49f4-be7a-dc9050ed8304.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
 ***
 
 ## Creating a Virtual Host

Create a domain named projectlamp or any name you choose.
Apache will be used, and it is set up to serve files from the /var/www/html directory.
#Create the directory for projectlamp:
```
sudo mkdir /var/www/projectlamp
```
```
sudo chown -R $USER:$USER /var/www/projectlamp
```
Then, under Apache's sites-available directory, create and open a new configuration file with:
```
sudo vi /etc/apache2/sites-available/projectlamp.conf
```
This will generate a new empty file. 
***
#To enter insert mode, press **I** on the keyboard and paste the following:
```
<VirtualHost *:80>
ServerName projectlamp
ServerAlias www.projectlamp
ServerAdmin webmaster@localhost
DocumentRoot /var/www/projectlamp
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combine
</VirtualHost>
```
Simply follow the instructions below to save and close the file:
Press the **esc** key on your keyboard.
Type **wq**, where w stands for write and q stands for quit. To save the file, press **ENTER**.
***
#To show the new file in the sites-available directory
```
sudo ls /etc/apache2/sites-available
```
***
<img
  src="https://user-images.githubusercontent.com/80969889/203690844-73d0a857-38cc-4a6e-a8c1-29c1939cd0af.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
 ***

#To activate the new virtual host, use the a2ensite command:
```
sudo a2ensite projectlamp
```
#To deactivate Apache's default website usage type:
```
sudo a2dissite 000-default
```
#To ensure that your configuration file is free of syntax problems, run:
```
sudo apache2ctl configtest
```
Finally, reload Apache to make these modifications effective:
```
sudo systemctl reload apache2
```
Your new website is currently operational!
***
#Create an index.html file to verify that the virtual host is functioning properly:
```
sudo echo 'Hello LAMP from hostname' $(curl -s http://<Public-IP-Address>/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://<Public-IP-Address>/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html
```
#Enter your IP address into your browser and try to view your website URL:
```
http://<Public-IP-Address>:80
```

***
<img
  src="https://user-images.githubusercontent.com/80969889/203692494-1a2779be-be90-409b-b11b-1d99afc20f5a.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
 ***
 
 ## Add PHP to the Website
 
index.html always takes precedence over  index.php in Apache's default DirectoryIndex settings.
To modify this behaviour, update the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed under the DirectoryIndex directive:
```
sudo vim /etc/apache2/mods-enabled/dir.conf
```


This will be seen in the text editor:
***
<IfModule mod_dir.c>
***
#Change this: DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
***
To this: DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
***
</IfModule>
***
Reload Apache after saving and closing the file in order for the changes to take effect:


```
sudo systemctl reload apache2
```

Finally, we will create a PHP script to test that PHP is correctly installed and configured on your server.
***
#Create a new file named index.php inside your custom web root folder:

```
vim /var/www/projectlamp/index.php
```

#Type inside the file:

```
<?php

phpinfo();
```

Save and close the file. When you refresh the web page in your browser, you should see something like the picture below, demonstrating that the PHP installation is working successfully. Because the PHP file contains crucial information about the PHP environment as well as the Ubuntu server, it is advisable to remove it afterwards. This is possible using rm:

```
sudo rm /var/www/projectlamp/index.php
```

You may always redo this page.

    
***
<img
  src="https://user-images.githubusercontent.com/80969889/203696395-4358a215-fd9a-4aaf-a36d-bef420eacf3e.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
 





