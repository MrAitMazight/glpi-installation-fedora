# Create GLPI Database

GLPI requires a database to store users, assets, tickets and configuration.

In this project we use MariaDB.

---

## Step 1 — Connect to MariaDB

Open the terminal and run:

```bash
sudo mysql -u root -p
```
Explanation:

This command connects to the MariaDB server as the root administrator.

---

## Step 2 — Create the GLPI database

Run the following command:

```bash
CREATE DATABASE glpi_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
Explanation:

This creates a new database called glpi_db.

The UTF8MB4 character set is recommended for GLPI.

---

## Step 3 — Create a database user

```bash
CREATE USER 'glpi_user'@'localhost' IDENTIFIED BY 'StrongPassword';
```
Explanation:

This creates a dedicated user for GLPI.

Using a dedicated user improves security.

---

## Step 4 — Grant permissions
```bash
GRANT ALL PRIVILEGES ON glpi_db.* TO 'glpi_user'@'localhost';
```
Explanation:

This command allows the GLPI user to manage the database.

---

## Step 5 — Reload privileges
```bash
FLUSH PRIVILEGES;
```
Explanation:

This reloads the privilege tables.

---

## Step 6 — Exit MariaDB
```bash
EXIT;
```
---

## Database information used in GLPI installation

When installing GLPI in the browser use:

Database server: localhost  
Database name: glpi_db  
Database user: glpi_user  
Database password: StrongPassword
