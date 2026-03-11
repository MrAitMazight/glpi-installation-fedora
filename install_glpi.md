# GLPI Installation

## Step 1: Go to web directory

cd /var/www/html

## Step 2: Download GLPI

wget https://github.com/glpi-project/glpi/releases/download/11.0.0/glpi-11.0.0.tgz

## Step 3: Extract the archive

tar -xvzf glpi-11.0.0.tgz

## Step 4: Set permissions

sudo chown -R apache:apache /var/www/html/glpi
sudo chmod -R 755 /var/www/html/glpi

## Step 5: SELinux Sur Fedora Linux :

sudo chcon -R -t httpd_sys_rw_content_t /var/www/html/glpi

## Step 6: Firewall
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload

## Step 7: Apache VirtualHost Configuration

Create Apache configuration file:

sudo nano /etc/httpd/conf.d/glpi.conf

Add:

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

## Step 8: Restart Apache

sudo systemctl restart httpd

## Step 9: Open GLPI

Open in browser:

http://SERVER_IP
