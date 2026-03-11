# MariaDB Installation

MariaDB is the database server used by GLPI.

## Install MariaDB
```bash
sudo dnf install mariadb-server -y
```
## Start the service
```bash
sudo systemctl enable --now mariadb
```
## Verify the service
```bash
sudo systemctl status mariadb
```
## Secure MariaDB
```bash
sudo mysql_secure_installation
```
Explanation:
This command improves database security.

It will ask to:

- Set root password
- Remove anonymous users
- Disable remote root login
- Remove test database
