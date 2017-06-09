# Configure the CM repo to install the 5.10 release
`sed -i 's$6/x86_64/cm/5/$6/x86_64/cm/5.10/$' /etc/yum.repos.d/cloudera-manager.repo`

# ls of directory
```
[root@ip-172-31-34-150 ~]# ls /etc/yum.repos.d
cloudera-manager.repo  mysql-community-source.repo     redhat-rhui.repo          rhel-source.repo
mysql-community.repo   redhat-rhui-client-config.repo  redhat-rhui.repo.rpmsave  rhui-load-balancers.conf
```


# CM Database preparation
Database preparation

```bash
# create temp user before (as root is blocked for remote connection)
/usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-40-167.eu-west-1.compute.internal -P 3306 -u temp -p --scm-host ip-172-31-34-150.eu-west-1.compute.internal cmf cmf cmf
```
Result
```
[root@ip-172-31-34-150 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-40-167.eu-west-1.compute.internal -P 3306 -u temp -p --scm-host ip-172-31-34-150.eu-west-1.compute.internal cmf cmf cmf
Enter database password:
JAVA_HOME=/usr/java/jdk1.8.0_111
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_111/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
[root@ip-172-31-34-150 ~]#
```
