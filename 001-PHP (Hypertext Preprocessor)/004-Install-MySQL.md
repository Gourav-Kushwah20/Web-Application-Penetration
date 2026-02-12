
# 🗄️ Installing MySQL Server

![alt text](./img/mysql.png)

## 📥 Download MySQL APT Config Package

### Install prerequisites:

```bash
apt install wget
```

### Download package:

> https://dev.mysql.com/downloads/

```bash
wget https://dev.mysql.com/get/mysql-apt-config_0.8.36-1_all.deb
```

### Install it:

```bash
apt install ./mysql-apt-config_0.8.36-1_all.deb
```
     

### Update packages:

```bash
apt update
```
---

## 🗄️ Install MySQL
- check and select on your OS version:`Debian GNU/Linux 13 (trixie)`

```bash
PRETTY_NAME="Debian GNU/Linux 13 (trixie)"
NAME="Debian GNU/Linux"
VERSION_ID="13"
VERSION="13 (trixie)"
VERSION_CODENAME=trixie
DEBIAN_VERSION_FULL=13.2
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
```   
```bash
apt install mysql-community-server
```

## 🚀 Enable and Start MySQL

```bash
systemctl restart mysql.service
```

```bash
systemctl enable mysql.service
```

---

## 🔎 Verify MySQL is Running

```bash
netstat -nltup
```

Check specifically for port **3306**:

```bash
netstat -nltup | grep 3306
```

---

## 🔐 Run Secure Setup

```bash
mysql_secure_installation
```

---

## 🛡️ Access MySQL

```bash
mysql -u root -p
```

### Inside MySQL:

```sql
show databases;
```

### Optional: Create a Remote Root User

```sql
CREATE USER 'root'@'%' IDENTIFIED WITH caching_sha2_password BY 'your_password';
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
```

---

## 🔐 Enabling SSL on Apache

### ✔️ Enable SSL module:

```bash
a2enmod ssl
```

### 🔄 Restart Apache:

```bash
systemctl restart apache2.service
```

### 🌐 Enable default SSL site:

```bash
a2ensite default-ssl
```

### ♻️ Reload Apache:

```bash
systemctl reload apache2
```

### 📡 Check services:

```bash
netstat -nltup
```

```bash
service apache2 reload
```

---

## 🛠️ Creating a Self-Signed SSL Certificate

### 📁 Create SSL directory:

```bash
mkdir /etc/apache2/ssl
```

### 🧾 Generate certificate:

```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/armour.local.key -out /etc/apache2/ssl/armour.local.crt
```

## 🔎 Verify SSL Files

### 🔐 View SSL private key:

```bash
cat /etc/apache2/ssl/armour.local.key
```

### 📄 View SSL certificate:

```bash
cat /etc/apache2/ssl/armour.local.crt
```

---

## 📝 Update Hosts File

```bash
vim /etc/hosts
```

### 🧩 Example entry:

```text
192.168.1.28   armour.local   www.armour.local
```

---

## 🛠️ phpMyAdmin Installation

### ⬇️ Download and unzip:

https://www.phpmyadmin.net/files/5.2.3/ 

```bash
wget https://files.phpmyadmin.net/phpMyAdmin/5.2.3/phpMyAdmin-5.2.3-all-languages.zip
```

```bash
unzip phpMyAdmin-5.2.3-all-languages.zip
```

### 📦 Move files:

```bash
mv -v phpMyAdmin-5.2.3-all-languages /var/www/html/phpmyadmin
```

### 🔧 Set ownership:

```bash
chown -Rv www-data:www-data /var/www/html/phpmyadmin
```
## Check `phpmyadmin`

http://192.168.1.50/phpmyadmin/


### ⚙️ Create phpMyAdmin Config File

```bash
cp -v /var/www/html/phpmyadmin/config.sample.inc.php /var/www/html/phpmyadmin/config.inc.php
```

```bash
chown -Rv www-data:www-data /var/www/html/phpmyadmin/config.inc.php
```

### 🔑 Generate a Blowfish Secret

```bash
pwgen 32 -1
```

### 📝 Edit phpMyAdmin Config

```bash
vim /var/www/html/phpmyadmin/config.inc.php
```

### ➕ Insert Secret:

```php
$cfg['blowfish_secret'] = 'obooj1weixe5beiVaiqu8iehu8theiXi';
```

---

```bash
chown -Rv www-data:www-data /var/www/html/phpmyadmin
```

```bash
systemctl restart apache2.service
```
