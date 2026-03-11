# PHP Installation

PHP is required to run GLPI.

## Install PHP and extensions
```bash
sudo dnf install php php-mysqlnd php-gd php-mbstring php-curl php-xml php-intl php-zip php-bcmath php-ldap -y
```
Explanation:

These extensions are required by GLPI.

## Verify PHP installation
```bash
php -v
```
