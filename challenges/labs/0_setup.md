* List the cloud provider you are using (AWS, GCE, Azure, other)
  * AWS - eu-west-1 - Ireland center
  * running 5 instance of type: m3.xlarge
* List the Linux release you have chosen
  Using the AMI ami-af6faad8: RHEL-6.5_HVM_GA-x86_64
  ```
  [root@ip-172-31-34-150 ~]# cat /etc/redhat-release
  Red Hat Enterprise Linux Server release 6.5 (Santiago)
  ```
* Show that the disk space on each node is at least 30 GB
  `lsblk && df -h`
```
[root@ip-172-31-40-167 ~]# lsblk && df -h
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  100G  0 disk
└─xvda1 202:1    0  100G  0 part /
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       99G  2.3G   92G   3% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
[root@ip-172-31-33-70 ~]# lsblk && df -h
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  100G  0 disk
└─xvda1 202:1    0  100G  0 part /
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       99G  2.3G   92G   3% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
[root@ip-172-31-44-94 ~]# lsblk && df -h
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  100G  0 disk
└─xvda1 202:1    0  100G  0 part /
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       99G  2.3G   92G   3% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
[root@ip-172-31-33-176 ~]# lsblk && df -h
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  100G  0 disk
└─xvda1 202:1    0  100G  0 part /
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       99G  2.3G   92G   3% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
[root@ip-172-31-34-150 ~]# lsblk && df -h
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  100G  0 disk
└─xvda1 202:1    0  100G  0 part /
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       99G  2.3G   92G   3% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```
* List the command and output for yum repolist enabled
  `yum repolist enabled`
  ```
  [root@ip-172-31-40-167 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, security
repo id                                          repo name                                                              status
rhui-REGION-client-config-server-6               Red Hat Update Infrastructure 2.0 Client Configuration Server 6             7
rhui-REGION-rhel-server-releases                 Red Hat Enterprise Linux Server 6 (RPMs)                               19,554
rhui-REGION-rhel-server-releases-optional        Red Hat Enterprise Linux Server 6 Optional (RPMs)                      11,247
rhui-REGION-rhel-server-rh-common                Red Hat Enterprise Linux Server 6 RH Common (RPMs)                        129
rhui-REGION-rhel-server-rhscl                    Red Hat Enterprise Linux Server 6 RHSCL (RPMs)                          8,234
repolist: 39,171
  ```
* Creation of users
  ```bash
  # defining the group ids to a consistent value across the cluster
  sudo groupadd -g 2010 conservative
  sudo groupadd -g 3010 labour
  sudo useradd -u 2000 -g conservative theresa
  sudo useradd -u 3000 -g labour jeremy
  ```

* Listing of `/etc/passwd`
```
theresa:x:2000:2010::/home/theresa:/bin/bash
jeremy:x:3000:3010::/home/jeremy:/bin/bash
/etc/passwd (END)
```

* Listing of `/etc/group`
```
conservative:x:2010:
labour:x:3010:
```
