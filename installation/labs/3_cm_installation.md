Installation of CM repository and setting of version
```bash
wget https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/cloudera-manager.repo -O /etc/yum.repos.d/cloudera-manager.repo
sed -i 's$6/x86_64/cm/5/$6/x86_64/cm/5.8.3/$' /etc/yum.repos.d/cloudera-manager.repo
yum install -y oracle-j2sdk1.7
```

Prepare the MySQL to generate the CM tables
```bash
mysql -p -u root
  grant all on *.* to 'temp'@'%' identified by 'temp' with grant option;

/usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-28-183.eu-west-1.compute.internal -P 3306 -u temp -p --scm-host ip-172-31-28-183.eu-west-1.compute.internal cmf cmf cmf
```

Remove temporary user and create table for oozie and hue

```bash
mysql -p -u root
  drop user 'temp'@'%';

  create database oozie;
  grant all privileges on oozie.* to 'oozie'@'localhost' identified by 'oozie';
  grant all privileges on oozie.* to 'oozie'@'%' identified by 'oozie';

  create database hue default character set utf8 default collate utf8_general_ci;
  grant all on hue.* to 'hue'@'%' identified by 'huepassword';
  select * from information_schema.schemata;

# link the mysql connector into the oozie libs
ln -s /usr/share/java/mysql-connector-java.jar /opt/cloudera/parcels/CDH/lib/oozie/lib/
```
