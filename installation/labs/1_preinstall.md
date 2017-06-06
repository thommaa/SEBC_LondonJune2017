sudo su - root

yum install nscd -y
service ntpd start
service nscd start

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

sysctl -w vm.swappiness=1
echo never > /sys/kernel/mm/transparent_hugepage/enabled

reboot now
