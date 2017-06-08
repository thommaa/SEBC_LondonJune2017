kinit thommaa@SEBC.CLOUDERA.COM

klist

```
[thommaa@ip-172-31-16-37 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_501
Default principal: thommaa@SEBC.CLOUDERA.COM

Valid starting     Expires            Service principal
06/08/17 05:52:35  06/09/17 05:52:35  krbtgt/SEBC.CLOUDERA.COM@SEBC.CLOUDERA.COM
	renew until 06/15/17 05:52:35
[thommaa@ip-172-31-16-37 ~]$ hadoop fs -ls
Found 7 items
drwx------   - thommaa supergroup          0 2017-06-07 06:17 .staging
drwxrwxrwx   - thommaa supergroup          0 2017-06-08 04:31 2015_11_18
drwxrwxrwx   - thommaa supergroup          0 2017-06-08 04:31 2015_11_19
drwxrwxrwx   - thommaa supergroup          0 2017-06-08 04:31 2015_11_20
drwxrwxrwx   - thommaa supergroup          0 2017-06-08 04:31 2015_11_21
drwxr-xr-x   - thommaa supergroup          0 2017-06-07 06:13 teragen-1GB
drwxr-xr-x   - thommaa supergroup          0 2017-06-07 06:17 terasort-1GB
```
