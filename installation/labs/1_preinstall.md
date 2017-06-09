** preparation of the node after creation**
```bash
sudo su - root

yum install nscd -y
service ntpd start
service nscd start
chkconfig ntpd on
chkconfig nscd on

yum update -y

# https://tecadmin.net/resize-root-ebs-volume-on-aws-linux-instance/

fdisk -uc /dev/xvda << EOF
p
d
n
p
1
2048

a
1
w
EOF

partprobe /dev/xvda1

# swappiness at runtime and after restart
sysctl -w vm.swappiness=1
echo 'vm.swappiness = 1' >> /etc/sysctl.conf
# hugepage during runtime and after reboot
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo 'echo never > /sys/kernel/mm/transparent_hugepage/enabled' >> /etc/rc.local
echo never > /sys/kernel/mm/transparent_hugepage/defrag
echo 'echo never > /sys/kernel/mm/transparent_hugepage/defrag' >> /etc/rc.local

# disable ip6v
cat >> /etc/sysctl.conf <<EOF
net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
EOF

sysctl -p
service iptables stop
service ip6tables stop
chkconfig ip6tables off
chkconfig iptables off

sed -i 's/SELINUX=.*/SELINUX=disabled/' /etc/sysconfig/selinux

reboot now
```

1. Check `vm.swappiness` on all your nodes
    * Set the value to `1` if necessary

```
cat /proc/sys/vm/swappiness
```

2. Show the mount attributes of all volumes
```
mount
```

3. Show the reserve space of any non-root, `ext`-based volumes
    * XFS volumes do not maintain reserve space
`lsblk`
4. Disable transparent hugepage support
`echo never > /sys/kernel/mm/transparent_hugepage/enabled`

5. List your network interface configuration
`ifconfig`

6. List forward and reverse host lookups using `getent` or `nslookup`


7. Show the <code>nscd</code> service is running
```
service nscd status
```

8. Show the <code>ntpd</code> service is running<br>
```
service ntpd status
```
