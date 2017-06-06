wget https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/cloudera-manager.repo -O /etc/yum.repos.d/cloudera-manager.repo
sed -i 's$6/x86_64/cm/5/$6/x86_64/cm/5.8.3/$' /etc/yum.repos.d/cloudera-manager.repo
yum install -y oracle-j2sdk1.7

/usr/share/cmf/schema/scm_prepare_database.sh mysql -h localhost -P 3306 -u root -p --scm-host ip-172-31-28-183.eu-west-1.compute.internal cmf cmf cmf
