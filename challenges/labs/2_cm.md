# Configure the CM repo to install the 5.10 release
`sed -i 's$6/x86_64/cm/5/$6/x86_64/cm/5.10/$' /etc/yum.repos.d/cloudera-manager.repo`

# ls of directory
```
[root@ip-172-31-34-150 ~]# ls /etc/yum.repos.d
cloudera-manager.repo  mysql-community-source.repo     redhat-rhui.repo          rhel-source.repo
mysql-community.repo   redhat-rhui-client-config.repo  redhat-rhui.repo.rpmsave  rhui-load-balancers.conf
```
