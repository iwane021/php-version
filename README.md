# php-version
PHP windows binaries including all standand extensions present in original PHP distribution

# check Listen port not used
```
open command prompt and type : netstat -aon
```

# Some Setting Apache
```
ScriptAlias /php5_6/ "C:/xampp/php5_6/"
<Directory "C:/xampp/php5_6">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8056
<VirtualHost *:8056>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php5_6
        Action application/x-httpd-php5_6 "/php5_6/php-cgi.exe"
    </FilesMatch>
</VirtualHost>


ScriptAlias /php7_1/ "C:/xampp/php7_1/"
<Directory "C:/xampp/php7_1">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8071
<VirtualHost *:8071>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php7_1
        Action application/x-httpd-php7_1 "/php7_1/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

# Setting Extension
![Screenshot](setting-extension-php-ini.png)
