ami-b22961c1
ssh -i /Users/thomma/Downloads/SEBC-thomma.pem ec2-user@54.77.254.56

General approach for the Cloudera-Manager-Installation-Guide
sudo su - root

1. Check `vm.swappiness` on all your nodes
    * Set the value to `1` if necessary
    cat /proc/sys/vm/swappiness
    sysctl -w vm.swappiness=1

2. Show the mount attributes of all volumes
mount

3. Show the reserve space of any non-root, `ext`-based volumes
    * XFS volumes do not maintain reserve space
    lsblk
4. Disable transparent hugepage support
echo never > /sys/kernel/mm/transparent_hugepage/enabled

5. List your network interface configuration
ifconfig

6. List forward and reverse host lookups using `getent` or `nslookup`


7. Show the <code>nscd</code> service is running

8. Show the <code>ntpd</code> service is running<br>
