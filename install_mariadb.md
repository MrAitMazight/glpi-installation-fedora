# MariaDB Installation

MariaDB is the database server used by GLPI.

## Install MariaDB

sudo dnf install mariadb-server -y

## Start the service

sudo systemctl enable --now mariadb

## Verify the service

sudo systemctl status mariadb

## Secure MariaDB

sudo mysql_secure_installation

Explanation:
This command improves database security.

It will ask to:

- Set root password
- Remove anonymous users
- Disable remote root login
- Remove test database
