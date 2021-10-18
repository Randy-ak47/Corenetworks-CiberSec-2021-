# INSTLACIÓN DE APACHE, MARIADB Y PHPMYADMIN
[Guia instalación](https://www.digitalocean.com/community/tutorials/como-instalar-el-servidor-web-de-apache-en-debian-9-es)
- $ sudo apt update
- $ sudo apt install apache2
- $ sudo ufw app list
- opcional $ sudo ufw allow 'WWW'
- $ sudo ufw status
- $ sudo systemctl status apache2
- $ sudo systemctl stop apache2
- $ sudo systemctl start apache2
- $ sudo systemctl restart apache2
- $ sudo systemctl reload apache2
- $ sudo systemctl disable apache2
- $ sudo systemctl enable apache2

- $ sudo apt install curl

# Instalación de MYSQL
- $ sudo apt install mysql-server
- $ sudo mysql

- $ sudo apt install php libapache2-mod-php php-mysql
- $ php -v
# Instalación de PHPMYADMIN
- $ sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl

- **En caso de error**

- $ mysql -u root -p
- UNINSTALL COMPONENT "file://component_validate_password";

- INSTALL COMPONENT "file://component_validate_password";

- $ sudo phpenmod mbstring
- $ sudo systemctl restart apache2
- **En caso de error de contraseña root**
- $ mysql
- ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'password';

- ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

## Proteger phpMyAdmin (ventana emergente)
- $ sudo nano /etc/apache2/conf-available/phpmyadmin.conf
- añadir -- AllowOverride All
- $ sudo systemctl restart apache2
- $ sudo nano /usr/share/phpmyadmin/.htaccess

```
AuthType Basic
AuthName "Restricted Files"
AuthUserFile /etc/phpmyadmin/.htpasswd
Require valid-user
```
- $ sudo htpasswd -c /etc/phpmyadmin/.htpasswd username
- **opcional**
- $ sudo htpasswd /etc/phpmyadmin/.htpasswd additionaluser

# Instalación de ftp
- $ apt install ftpd
- 





