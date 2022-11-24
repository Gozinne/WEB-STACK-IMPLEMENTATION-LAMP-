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

#### Requirements

* The following items are required to begin and complete this project.
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

### Installing Apache and Updating the Firewall

[Apache HTTP Server](https://httpd.apache.org/) is the most widely used web server software. 
The Apache Software Foundation develops and maintains Apache, which is free open-source software that is fast, dependable, and secure. 
It may be significantly customised using extensions and modules to meet the needs of a wide range of circumstances. 
Apache saves virtual host configuration files. All accessible configuration files may be found in the [directory](/etc/apache2/sites-available/).

Install Apache using Ubuntu’s package manager ‘apt’:

***
<img
  src="https://user-images.githubusercontent.com/80969889/203669331-a404ec1a-2089-4deb-b003-9cdd4b82a88b.mp4"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">



