# NamedManager\_Deploy

## deploy lnmp env

```text
yum install -y gcc gcc-c++ openssl curl curl-devel \
httpd \
php php-soap php-mysqlnd php-intl php-xml php-xmlrpc php-fpm php-gd php-ldap php-odbc php-pear php-mbstring php-snmp php-bcmath \
mariadb mariadb-server mariadb-libs mariadb-devel
```

修改nginx支持PHP解析

下载namedmanager安装包

```text
wget https://repos.jethrocarr.com/pub/amberdms/linux/centos/7/jethrocarr-custom/x86_64/namedmanager-bind-1.9.0-2.el7.centos.noarch.rpm
wget https://repos.jethrocarr.com/pub/amberdms/linux/centos/7/jethrocarr-custom/x86_64/namedmanager-www-1.9.0-2.el7.centos.noarch.rpm
```

安装namedmanager-www

```sql
yum localinstall -y namedmanager-www-1.9.0-2.el7.centos.noarch.rpm
```

```text
#cd /usr/share/namedmanager/resources/
#[root@bogon resources]# ./autoinstall.pl
```

数据库授权

```sql
mysql -uroot -p
```

```sql
grant all privileges on namedmanager.* to namedmanager@localhost identified by 'namedmanager';
flush privileges;
```

