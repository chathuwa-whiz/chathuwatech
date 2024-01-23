1. download xampp
    wget https://sourceforge.net/projects/xampp/files/XAMPP%20Linux/8.2.12/xampp-linux-x64-8.2.12-0-installer.run

3. give read,write,execute permissions to setup file
    chmod 755 xampp-linux-x64-8.2.12-0-installer.run
    (755 means read and execute access for everyone and write access to the owner of the file)

4. install
    sudo ./xampp-linux-x64-5.6.40-1-installer.run

5. httpd-xampp.conf error solve
    nano /opt/lampp/etc/extra/httpd-xampp.conf
   
    add these lines to above path
   
    <Directory "/opt/lampp/phpmyadmin">
     AllowOverride AuthConfig Limit
     Order allow,deny
     Allow from all
     Require all granted
     ErrorDocument 403 /error/XAMPP_FORBIDDEN.html.var
    </Directory>

7. phpmyadmin logout not showing
    nano /opt/lampp/phpmyadmin/config.inc.php
  
    $cfg['Servers'][$i]['auth_type'] = 'cookie';
    $cfg['Servers'][$i]['user'] = 'root';

8. uploaded images can't see
    chmod -R 777 /directory/
