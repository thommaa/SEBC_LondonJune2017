# MySQL server installation:

# Hostname:
```
[root@ip-172-31-40-167 ~]# hostname
ip-172-31-40-167.eu-west-1.compute.internal
```

# MySQL version
```
[root@ip-172-31-40-167 ~]# mysqld --version
mysqld  Ver 5.5.56-log for Linux on x86_64 (MySQL Community Server (GPL))
```

# MySQL databases Listing
  connect using `mysql -u root -p`
```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)

```

# Apendix:

Creation of tables and users:
```
CREATE DATABASE scm DEFAULT CHARACTER SET utf8;
grant all on scm.* TO 'scm'@'%' IDENTIFIED BY 'scm_password';

CREATE DATABASE rman DEFAULT CHARACTER SET utf8;
grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';

CREATE DATABASE hive DEFAULT CHARACTER SET utf8;
grant all on hive.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';

CREATE DATABASE oozie DEFAULT CHARACTER SET utf8;
grant all on oozie.* TO 'oozie'@'%' IDENTIFIED BY 'oozie_password';

CREATE DATABASE hue DEFAULT CHARACTER SET utf8;
grant all on hue.* TO 'hue'@'%' IDENTIFIED BY 'hue_password';

CREATE DATABASE sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';
```

Installation of client and connector jar
```bash
wget https://dev.mysql.com/get/mysql57-community-release-el6-11.noarch.rpm
sudo rpm -Uvh mysql57-community-release-el6-11.noarch.rpm
yum install -y mysql-community-client
wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.42.tar.gz
tar zxvf mysql-connector-java-5.1.42.tar.gz --strip=1 mysql-connector-java-5.1.42/mysql-connector-java-5.1.42-bin.jar
cp mysql-connector-java-5.1.42-bin.jar /usr/share/java/mysql-connector-java.jar
rm -f mysql-connector-java-5.1.42-bin.jar mysql-connector-java-5.1.42.tar.gz mysql57-community-release-el6-11.noarch.rpm
```
