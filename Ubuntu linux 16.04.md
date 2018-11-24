# 解鎖
```
  ps aux | grep apt
  kill processnumber
  kill -9 processnumber
  sudo rm -f /var/lib/dpkg/lock
  sudo rm /var/lib/apt/lists/* -vf
  sudo dpkg --configure -a
 ```
 # XAMPP
 ```
  sudo wget https://www.apachefriends.org/xampp-files/7.2.11/xampp-linux-x64-7.2.11-0-installer.run
  sduo chmod 777 xampp-linux-x64-7.2.11-0-installer.run 
  sudo ./xampp-linux-x64-7.2.11-0-installer.run 
  sudo /opt/lampp/lampp restart
  ```
  # DVWA
  ```
  sudo wget https://github.com/ethicalhack3r/DVWA/archive/master.zip
  sudo chmod 777 master.zip
  sudo unzip master.zip
  sudo mv DVWA-master /opt/lampp/htdocs
  cd /opt/lampp/htdocs/DVWA-master/config
  sudo mv config.inc.php.dist config.inc.php 
  sudo vim config.inc.php
  ----------------------------------------------------------------------------------------------------------------
$_DVWA[ 'db_password' ] = '';

$_DVWA[ 'recaptcha_public_key' ] = '6LfQNCYTAAAAALx0oAwtLHJlzNHXTKLl2UZjQjw-';
$_DVWA[ 'recaptcha_private_key' ] = '6LfQNCYTAAAAAHnvqCzw2lG95FD-RfomKHWf7Zob';

$_DVWA[ 'default_security_level' ] = 'low’;
-------------------------------------------------------------------------------------------------------------------
sudo vim /opt/lampp/etc/php.ini
sudo /opt/lampp/lampp restart 

sudo chmod 777 /opt/lampp/htdocs/DVWA-master/hackable/uploads
sudo chmod 777 /opt/lampp/htdocs/DVWA-master/external/phpids/0.6/lib/IDS/tmp/phpids_log.txt
sudo chmod 777 /opt/lampp/htdocs/DVWA-master/config/config.inc.php
```
# Mod Securtiy
```
