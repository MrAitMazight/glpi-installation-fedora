# GLPI Installation

## Step 1: Go to web directory
```bash
cd /var/www/html
```
## Step 2: Download GLPI
```bash
wget https://github.com/glpi-project/glpi/releases/download/11.0.0/glpi-11.0.0.tgz
```
## Step 3: Extract the archive
```bash
tar -xvzf glpi-11.0.0.tgz
```
## Step 4: Set permissions
```bash
sudo chown -R apache:apache /var/www/html/glpi
sudo chmod -R 755 /var/www/html/glpi
```
## Step 5: SELinux Sur Fedora Linux :
```bash
sudo chcon -R -t httpd_sys_rw_content_t /var/www/html/glpi
```
## Step 6: Firewall
```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
```
## Step 7: Open GLPI

Open in browser:
```bash
http://SERVER_IP
```
