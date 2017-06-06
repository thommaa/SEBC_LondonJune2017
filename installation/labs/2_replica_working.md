wget https://dev.mysql.com/get/mysql57-community-release-el6-11.noarch.rpm
sudo rpm -Uvh mysql57-community-release-el6-11.noarch.rpm
yum repolist all | grep mysql
yum-config-manager --disable mysql57-community
yum-config-manager --enable mysql55-community
yum repolist enabled | grep mysql
yum update -y
sudo yum install mysql-server
sudo service mysqld start
# not working: sudo systemctl start mysqld
sudo service mysqld stop
vi /etc/my.cnf
rm -f /var/lib/mysql/ib_logfile0 /var/lib/mysql/ib_logfile1
sudo service mysqld start
/usr/bin/mysql_secure_installation
# mysql root password: clouderaSEBC
mysql -u root -p
CREATE DATABASE amon DEFAULT CHARACTER SET utf8;
grant all on amon.* TO 'user'@'%' IDENTIFIED BY 'password';
CREATE DATABASE rman DEFAULT CHARACTER SET utf8;
grant all on rman.* TO 'user'@'%' IDENTIFIED BY 'password';
CREATE DATABASE metastore DEFAULT CHARACTER SET utf8;
grant all on metastore.* TO 'user'@'%' IDENTIFIED BY 'password';
CREATE DATABASE sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* TO 'user'@'%' IDENTIFIED BY 'password';
CREATE DATABASE nav DEFAULT CHARACTER SET utf8;
grant all on nav.* TO 'user'@'%' IDENTIFIED BY 'password';
CREATE DATABASE navms DEFAULT CHARACTER SET utf8;
grant all on navms.* TO 'user'@'%' IDENTIFIED BY 'password';

# install connector jar
wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.42.tar.gz
tar zxvf mysql-connector-java-5.1.42.tar.gz --strip=1 mysql-connector-java-5.1.42/mysql-connector-java-5.1.42-bin.jar
cp mysql-connector-java-5.1.42-bin.jar /usr/share/java/mysql-connector-java.jar
# copy via ssh to /tmp for other hosts
cp /tmp/mysql-connector-java-5.1.42-bin.jar /usr/share/java/mysql-connector-java.jar

# Master Slave configuration
GRANT REPLICATION SLAVE ON *.* TO 'user'@'ip-172-31-29-116.eu-west-1.compute.internal' IDENTIFIED BY 'password';

mysql> SHOW MASTER STATUS;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000004 |      293 |              |                  |
+-------------------------+----------+--------------+------------------+
1 row in set (0.00 sec)

# Slave
CHANGE MASTER TO MASTER_HOST='172.31.28.183', MASTER_USER='root', MASTER_PASSWORD='clouderaSEBC', MASTER_LOG_FILE='mysql_binary_log.000004', MASTER_LOG_POS=293;
START SLAVE;






mysql> START SLAVE;
Query OK, 0 rows affected (0.00 sec)

mysql> SHOW SLAVE STATUS \G
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: 172.31.28.183
                  Master_User: user
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql_binary_log.000005
          Read_Master_Log_Pos: 479
               Relay_Log_File: mysqld-relay-bin.000003
                Relay_Log_Pos: 632
        Relay_Master_Log_File: mysql_binary_log.000005
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 479
              Relay_Log_Space: 942
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 1
1 row in set (0.00 sec)
