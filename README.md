# Local Development for WordPress 5.2.0 using nginx + php-fpm + mariadb (mysql) on Windows 10

Using WordPress + LEMP stack for local development.

## Tech Stack

* Docker Toolbox (using Windows 10 Home Edition)
* WordPress Version 5.2.0 (latest)
* nginx 1.15.2 (latest) - this is our web server
* mariadb (latest) - similar to mysql, this is our database
* docker-file.yml relies on a .env (may include a dummy file into repo for an example)

## Local Volumes

* MySQL DB data: contains all of our mysql/mariadb data from the changes we made in WordPress
* ./wordpress: contains our entire wordpress app - may reduce this to just wp-config.php and our themes/plugins directories
* SSL certifcates/data
* Additional PHP.ini config (make additions for WP - i.e. max_execution_time)
* nginx access/error log files
* nginx.conf file

### Run it

* Make sure docker and docker-compose are installed to your machine
* Run "docker-compose up -d"
* Navigate to http://hostmachineip:port in browser
* Run 5 min install for WordPress
* Dev!
* To shut down docker and preserve your volumes (i.e. your mysql data and files!!!), type "$ docker-compose down"

### To Dos:

* Add phpmyadmin for a gui to edit DB
* Only include wp-content/themes and wp-content/plugins directories - not WP core files
* Use composer
* Install PECL/Pear modules to php 7.3.4