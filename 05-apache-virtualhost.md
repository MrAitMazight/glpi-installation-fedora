## Step 1: Apache VirtualHost Configuration

Create Apache configuration file:
```bash
sudo nano /etc/httpd/conf.d/glpi.conf
```
Add:
```bash
<VirtualHost *:80>
    ServerName SERVER_IP
    DocumentRoot /var/www/html/glpi/public

    <Directory /var/www/html/glpi/public>
        Require all granted
        RewriteEngine On

        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteRule ^(.*)$ index.php [QSA,L]
    </Directory>
</VirtualHost>
```
## Step 2: Restart Apache
```bash
sudo systemctl restart httpd
```
