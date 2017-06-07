Create linux user (on all machines in the cluster)
```bash
useradd thommaa -m -u 501
# useradd USER -g GROUP -u UID
```

Create HDFS home and chown it to user
```bash
sudo -u hdfs hdfs dfs -mkdir /user/thommaa
sudo -u hdfs hdfs dfs -chown -R thommaa /user/thommaa
```

Switch to user
```bash
sudo su - thommaa
# check the access and folder
hdfs dfs -ls
hdfs dfs -ls /user/thommaa
HDexample=/opt/cloudera/parcels/CDH/lib/hadoop-mapreduce
time hadoop jar ${HDexample}/hadoop-mapreduce-examples.jar teragen \
             -Dmapreduce.job.maps=4 \
             -Ddfs.block.size=33554432 \
             10000000 /user/thommaa/teragen-1GB             
```

Results from teragen / including time
```
17/06/07 06:13:41 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-37.eu-west-1.compute.internal/172.31.16.37:8032
17/06/07 06:13:42 INFO terasort.TeraSort: Generating 10000000 using 4
17/06/07 06:13:42 INFO mapreduce.JobSubmitter: number of splits:4
17/06/07 06:13:42 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/06/07 06:13:42 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1496825201524_0007
17/06/07 06:13:42 INFO impl.YarnClientImpl: Submitted application application_1496825201524_0007
17/06/07 06:13:42 INFO mapreduce.Job: The url to track the job: http://ip-172-31-16-37.eu-west-1.compute.internal:8088/proxy/application_1496825201524_0007/
17/06/07 06:13:42 INFO mapreduce.Job: Running job: job_1496825201524_0007
17/06/07 06:13:48 INFO mapreduce.Job: Job job_1496825201524_0007 running in uber mode : false
17/06/07 06:13:48 INFO mapreduce.Job:  map 0% reduce 0%
17/06/07 06:13:58 INFO mapreduce.Job:  map 100% reduce 0%
17/06/07 06:13:59 INFO mapreduce.Job: Job job_1496825201524_0007 completed successfully
17/06/07 06:14:00 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=495976
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=337
		HDFS: Number of bytes written=1000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=33434
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=33434
		Total vcore-seconds taken by all map tasks=33434
		Total megabyte-seconds taken by all map tasks=34236416
	Map-Reduce Framework
		Map input records=10000000
		Map output records=10000000
		Input split bytes=337
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=336
		CPU time spent (ms)=28470
		Physical memory (bytes) snapshot=1483190272
		Virtual memory (bytes) snapshot=6251696128
		Total committed heap usage (bytes)=1740111872
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=21472776955442690
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=1000000000

real	0m21.310s
user	0m6.191s
sys	0m0.286s
```

```bash
time hadoop jar ${HDexample}/hadoop-mapreduce-examples.jar terasort \
       /user/thommaa/teragen-1GB /user/thommaa/terasort-1GB
```

Results from terasort / including time
```
17/06/07 06:16:06 INFO terasort.TeraSort: starting
17/06/07 06:16:08 INFO input.FileInputFormat: Total input paths to process : 4
Spent 132ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 135ms
Sampling 10 splits of 32
Making 8 from 100000 sampled records
Computing parititions took 810ms
Spent 948ms computing partitions.
17/06/07 06:16:08 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-37.eu-west-1.compute.internal/172.31.16.37:8032
17/06/07 06:16:09 INFO mapreduce.JobSubmitter: number of splits:32
17/06/07 06:16:09 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1496825201524_0008
17/06/07 06:16:09 INFO impl.YarnClientImpl: Submitted application application_1496825201524_0008
17/06/07 06:16:09 INFO mapreduce.Job: The url to track the job: http://ip-172-31-16-37.eu-west-1.compute.internal:8088/proxy/application_1496825201524_0008/
17/06/07 06:16:09 INFO mapreduce.Job: Running job: job_1496825201524_0008
17/06/07 06:16:16 INFO mapreduce.Job: Job job_1496825201524_0008 running in uber mode : false
17/06/07 06:16:16 INFO mapreduce.Job:  map 0% reduce 0%
...
17/06/07 06:16:47 INFO mapreduce.Job:  map 94% reduce 0%
17/06/07 06:16:52 INFO mapreduce.Job:  map 100% reduce 0%
...
17/06/07 06:17:02 INFO mapreduce.Job:  map 100% reduce 100%
17/06/07 06:17:02 INFO mapreduce.Job: Job job_1496825201524_0008 completed successfully
17/06/07 06:17:02 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=443038051
		FILE: Number of bytes written=885319159
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1000003904
		HDFS: Number of bytes written=1000000000
		HDFS: Number of read operations=120
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters
		Launched map tasks=32
		Launched reduce tasks=8
		Data-local map tasks=32
		Total time spent by all maps in occupied slots (ms)=273670
		Total time spent by all reduces in occupied slots (ms)=88192
		Total time spent by all map tasks (ms)=273670
		Total time spent by all reduce tasks (ms)=88192
		Total vcore-seconds taken by all map tasks=273670
		Total vcore-seconds taken by all reduce tasks=88192
		Total megabyte-seconds taken by all map tasks=280238080
		Total megabyte-seconds taken by all reduce tasks=90308608
	Map-Reduce Framework
		Map input records=10000000
		Map output records=10000000
		Map output bytes=1020000000
		Map output materialized bytes=437263254
		Input split bytes=3904
		Combine input records=0
		Combine output records=0
		Reduce input groups=10000000
		Reduce shuffle bytes=437263254
		Reduce input records=10000000
		Reduce output records=10000000
		Spilled Records=20000000
		Shuffled Maps =256
		Failed Shuffles=0
		Merged Map outputs=256
		GC time elapsed (ms)=4250
		CPU time spent (ms)=171810
		Physical memory (bytes) snapshot=17848893440
		Virtual memory (bytes) snapshot=62867095552
		Total committed heap usage (bytes)=21155020800
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=1000000000
	File Output Format Counters
		Bytes Written=1000000000
17/06/07 06:17:02 INFO terasort.TeraSort: done

real	0m57.182s
user	0m7.913s
sys	0m0.393s

```
