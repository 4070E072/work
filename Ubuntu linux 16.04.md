# [2]Ubuntu linux 16.04平台測試環境建置:XAMPP + DVWA + Modsecurity
# [2.1]Ubuntu linux 16.04 web平台測試環境建置:XAMPP
# [2.2]Ubuntu linux 16.04 web漏洞平台測試環境建置:XAMPP + DVWA
# [2.3]Ubuntu linux 16.04 web攻防平台測試環境建置:XAMPP + DVWA + Modsecurity 

```
  apt-get update
  ps aux | grep apt
  kill processnumber
  kill -9 processnumber
  sudo rm /var/lib/dpkg/lock
  sudo dpkg --configure -a
 ``` 
  sudo apt-get install apache2 php libapache2-mod-php php-curl php-mcrypt php-mbstring phpunit php-gd -y     

  sudo apt-get install mysql-server php-mysqli -y
  sudo service apache2 restart

  cd /var/www/html
  sudo wget clone https://github.com/ethicalhack3r/DVWA.git
  sudo cp DVWA/config/config.inc.php.dist DVWA/config/config.inc.php

  sudo vim DVWA/config/config.inc.php
-----------------------------------------------------
  $_DVWA[ 'db_user' ] = 'root';
  $_DVWA[ 'db_password' ] = 'xxxxxxxxxx';

  $_DVWA[ 'recaptcha_public_key' ] = 'xxxxxxxxxxxxxx';
  $_DVWA[ 'recaptcha_private_key' ] = 'xxxxxxxxxxxxx';

  $_DVWA[ 'default_security_level' ] = 'low';
-----------------------------------------------------

  sudo vim /etc/php/7.0/apache2/php.ini
-----------------------------------------------------
  allow_url_include = On
-----------------------------------------------------
  sudo chmod 777  /var/www/html/DVWA/hackable/uploads/
  sudo chmod  777 /var/www/html/DVWA/external/phpids/0.6/lib/IDS/tmp/phpids_log.txt
  sudo service apache2 restart
  
  ```
  sudo su  ##ROOT權限
  sudo apt-get update ##更新
  wget https://www.apachefriends.org/xampp-files/7.2.11/xampp-linux-x64-7.2.11-0-installer.run  ##官網的最新下載連結
  chmod +x xampp-linux-x64-7.2.11-0-installer.run ##開啟執行權限
  ./xampp-linux-x64-7.2.11-0-installer.run  ##執行xampp安裝檔
  sudo /opt/lampp/xampp start  ##到/opt/lampp/裡面的xampp 並且執行他
  
  
  sudo wget https://github.com/ethicalhack3r/DVWA/archive/master.zip  ##下載DVWA
  cd home  ##到 HOME
  sudo unzip master.zip  ##解壓縮 剛剛下載的DVWA壓縮檔(檔名叫做master.zip)
  sudo mv DVWA-master /opt/lampp/htdocs/ ##把剛剛解壓縮的檔案移到/opt/lampp/htdocs/
  cd /opt/lampp/htdocs/DVWA-master/config/ ##移動到/opt/lampp/htdocs/DVWA-master/config/
  sudo cp config.inc.php.dist config.inc.php  ##將config.inc.php.dist複製成config.inc.php
  
  
  sudo vim config.inc.php  ##進入記事本編輯
  
  $_DVWA = array();
  $_DVWA[ 'db_server' ]   = '127.0.0.1';
  $_DVWA[ 'db_database' ] = 'dvwa';
  $_DVWA[ 'db_user' ]     = 'root';
  $_DVWA[ 'db_password' ] = 'p@ssw0rd';

  
