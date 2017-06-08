```
[root@ip-172-31-16-37 ~]# sudo su - thommaa
[thommaa@ip-172-31-16-37 ~]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-24-30.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-24-30.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM
Enter username for jdbc:hive2://ip-172-31-24-30.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM: thommaa
Enter password for jdbc:hive2://ip-172-31-24-30.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-24-30.eu-west-1.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170608071818_e5b8c52f-d6d7-40bb-bd1d-ca596c569ec6): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608071818_e5b8c52f-d6d7-40bb-bd1d-ca596c569ec6); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20170608071818_e5b8c52f-d6d7-40bb-bd1d-ca596c569ec6): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608071818_e5b8c52f-d6d7-40bb-bd1d-ca596c569ec6); Time taken: 0.158 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.349 seconds)
0: jdbc:hive2://ip-172-31-24-30.eu-west-1.com>
```


Create the priviledges
```
CREATE ROLE sentry_admin;
GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
GRANT ROLE sentry_admin TO GROUP {your_primary};
SHOW TABLES;
```

Create additional users:
```
sudo groupadd selector
sudo groupadd inserters
sudo useradd -u 1100 -g selector george
sudo useradd -u 1200 -g inserters ferdinand
kadmin.local: add_principal george
kadmin.local: add_principal ferdinand
```


kinit as george, then login to beeline

```
[george@ip-172-31-24-30 ~]$ kinit
Password for george@SEBC.CLOUDERA.COM:
[george@ip-172-31-24-30 ~]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> show tables;
No current connection
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM: george
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM: ******
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170608084747_deaafc68-a032-41d2-8320-59aff7cd6688): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608084747_deaafc68-a032-41d2-8320-59aff7cd6688); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20170608084747_deaafc68-a032-41d2-8320-59aff7cd6688): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608084747_deaafc68-a032-41d2-8320-59aff7cd6688); Time taken: 0.127 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.306 seconds)
0: jdbc:hive2://localhost:10000/default>
```

kinit as ferdinand and use beeline
```
[ferdinand@ip-172-31-24-30 ~]$ kinit
Password for ferdinand@SEBC.CLOUDERA.COM:
[ferdinand@ip-172-31-24-30 ~]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM: ferdinand
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-24-30.eu-west-1.compute.internal@SEBC.CLOUDERA.COM: *********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170608084949_d1984a97-2497-4461-be7f-a871e07e3506): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608084949_d1984a97-2497-4461-be7f-a871e07e3506); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20170608084949_d1984a97-2497-4461-be7f-a871e07e3506): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608084949_d1984a97-2497-4461-be7f-a871e07e3506); Time taken: 0.125 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.302 seconds)
0: jdbc:hive2://localhost:10000/default>
```
