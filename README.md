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
sudo chown -R $USER:$USER /var/www/projectlamp
```
Then, create and open a new configuration file in Apache’s sites-available directory using your preferred command-line editor. Here, we’ll be using vi or vim (They are the same by the way):

sudo vi /etc/apache2/sites-available/projectlamp.conf

This will create a new blank file. Paste in the following bare-bones configuration by hitting on i on the keyboard to enter the insert mode, and paste the text:

<VirtualHost *:80>

ServerName projectlamp

ServerAlias www.projectlamp

ServerAdmin webmaster@localhost

DocumentRoot /var/www/projectlamp

ErrorLog ${APACHE_LOG_DIR}/error.log

CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>

To save and close the file, simply follow the steps below:

1. Hit the esc button on the keyboard

2. Type:

3. Type wq. w for write and q for quit

4. Hit ENTER to save the file

You can use the ls command to show the new file in the sites-available directory

sudo ls /etc/apache2/sites-available

You will see something like this;

000-default.conf default-ssl.conf projectlamp.conf

With this VirtualHost configuration, we’re telling Apache to serve projectlamp using /var/www/projectlampl as its web root directory. If you would like to test Apache without a domain name, you can remove or comment out the options ServerName and ServerAlias by adding a # character in the beginning of each option’s lines. Adding the # character there will tell the program to skip processing the instructions on those lines.

You can now use a2ensite command to enable the new virtual host:

sudo a2ensite projectlamp

You might want to disable the default website that comes installed with Apache. This is required if you’re not using a custom domain name, because in this case Apache’s default configuration would overwrite your virtual host. To disable Apache’s default website use a2dissite command, type:

sudo a2dissite 000-default

To make sure your configuration file doesn’t contain syntax errors, run:

sudo apache2ctl configtest

Finally, reload Apache so these changes take effect:

sudo systemctl reload apache2

Your new website is now active, but the web root /var/www/projectlamp is still empty. Create an index.html file in that location so that we can test that the virtual host works as expected:

sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html

Now go to your browser and try to open your website URL using IP address:

http://<Public-IP-Address>:80

If you see the text from ‘echo’ command you wrote to index.html file, then it means your Apache virtual host is working as expected. In the output you will see your server’s public hostname (DNS name) and public IP address. You can also access your website in your browser by public DNS name, not only by IP – try it out, the result must be the same (port is optional)

http://<Public-DNS-Name>:80

You can leave this file in place as a temporary landing page for your application until you set up an index.php file to replace it. Once you do that, remember to remove or rename the index.html file from your document root, as it would take precedence over an index.php file by default.

STEP 5 — ENABLE PHP ON THE WEBSITE

With the default DirectoryIndex settings on Apache, a file named index.html will always take precedence over an index.php file. This is useful for setting up maintenance pages in PHP applications, by creating a temporary index.html file containing an informative message to visitors. Because this page will take precedence over the index.php page, it will then become the landing page for the application. Once maintenance is over, the index.html is renamed or removed from the document root, bringing back the regular application page.

In case you want to change this behavior, you’ll need to edit the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed within the DirectoryIndex directive:

sudo vim /etc/apache2/mods-enabled/dir.conf

<IfModule mod_dir.c>

#Change this:

#DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm

#To this:

DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm

</IfModule>

After saving and closing the file, you will need to reload Apache so the changes take effect:

sudo systemctl reload apache2

Finally, we will create a PHP script to test that PHP is correctly installed and configured on your server.

Now that you have a custom location to host your website’s files and folders, we’ll create a PHP test script to confirm that Apache is able to handle and process requests for PHP files.

Create a new file named index.php inside your custom web root folder:

vim /var/www/projectlamp/index.php

This will open a blank file. Add the following text, which is valid PHP code, inside the file:

<?php

phpinfo();

When you are finished, save and close the file, refresh the page and you will see a page similar to this:

This page provides information about your server from the perspective of PHP. It is useful for debugging and to ensure that your settings are being applied correctly.

If you can see this page in your browser, then your PHP installation is working as expected.

After checking the relevant information about your PHP server through that page, it’s best to remove the file you created as it contains sensitive information about your PHP environment -and your Ubuntu server. You can use rm to do so:

sudo rm /var/www/projectlamp/index.php

You can always recreate this pa
    











