wamp配置：
第一步>>>>
找到apache目录下：
【第一步】
../conf/httpd.conf文件
修改：改为自定义路径
```ini
DocumentRoot "E:/1php"
<Directory "E:/1php/">
```
【第二步】
找到apache目录下：
../conf/extra/httpd-vhosts.conf文件
修改域名：改为自定义域名
```ini
<VirtualHost *:80>
  ServerName www.ruj.com
  ServerAlias ruj.com
  DocumentRoot "e:/1php"
  <Directory "e:/1php/">
    Options +Indexes +Includes +FollowSymLinks +MultiViews
    AllowOverride All
    Require local
  </Directory>
</VirtualHost>
```
【关于 mysql 编码】
查询编码：`show variables like 'character_set%';`
在[mysqld]段落增加：
`character_set_server=utf8` 。重启MySQL服务即可。
