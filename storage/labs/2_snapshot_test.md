Execute on your local machine to copy to AWS
''
# scp zip file to local drive in /tmp folder
scp -i /Users/thomma/Downloads/SEBC-thomma.pem Downlds/SEBC-master.zip ec2-user@52.19.74.225:/tmp/
''

Connect per SSH to cluster node (where file was copied)
'''
# switch into hdfs user
sudo su - hdfs
hdfs dfs -mkdir precious
hdfs dfs -put /tmp/SEBC-master.zip precious/
# allow snapshot creation
hdfs dfsadmin -allowSnapshot /user/hdfs/precious
# create snapshot
hdfs dfs -createSnapshot precious sebc-hdfs-test
# try deleting folder -> result is execption
hdfs dfs -rm -f -R precious
# file can be deleted
hdfs dfs -rm precious/SEBC-master.zip
# restore file by coping from snapshot / alternative in CM UI
hdfs dfs -cp /user/hdfs/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /user/hdfs/precious
'''
