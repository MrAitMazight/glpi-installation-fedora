# Apache Installation on Fedora 43

Apache is the web server used to host the GLPI application.

## Step 1: Update the system

```bash
sudo dnf update -y
```
Explanation:
This command updates all installed packages.

## Step 2: Install Apache
```bash
sudo dnf install httpd -y
```
Explanation:
This installs the Apache HTTP Server.

## Step 3: Start Apache service
```bash
sudo systemctl enable --now httpd
```
Explanation:
This command starts Apache and enables it at system boot.

## Step 4: Verify Apache status
```bash
sudo systemctl status httpd
```
If the service is running, Apache is installed correctly.

## Step 5: Test Apache in browser

Open a browser and go to:
```bash
http://SERVER_IP
```
You should see the Fedora Apache test page.
