**In CM UI**: creation of new user for peer connection: `bdruser`

Following user roles tried:
* BDR administrator **not powerful enough**
* Cluster Administrator **also limited privileges**: `does not have sufficient permission`
* Full Administrator **-> working**

**Alternative approach**

With AWS configured completely open on public IPs and adding the mapping of the second cluser public->private->hostnames to /etc/hosts both BDR and distcp are completing
@leonceda
--> distcp working and successful completion
--> BDR failing after 60% in map step


```bash
[hdfs@ip-172-31-29-116 ~]$ hadoop distcp webhdfs://176.34.129.78:50070/user/hdfs/teragen-leonceda /user/hdfs/teragen-leonceda
17/06/06 12:12:08 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[webhdfs://176.34.129.78:50070/user/hdfs/teragen-leonceda], targetPath=/user/hdfs/teragen-leonceda, targetPathExists=true, filtersFile='null'}
17/06/06 12:12:08 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-37.eu-west-1.compute.internal/172.31.16.37:8032
17/06/06 12:12:09 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
17/06/06 12:12:09 INFO tools.SimpleCopyListing: Build file listing completed.
17/06/06 12:12:09 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/06/06 12:12:09 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/06/06 12:12:09 INFO tools.DistCp: Number of paths in the copy list: 4
17/06/06 12:12:09 INFO tools.DistCp: Number of paths in the copy list: 4
17/06/06 12:12:09 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-37.eu-west-1.compute.internal/172.31.16.37:8032
17/06/06 12:12:09 INFO mapreduce.JobSubmitter: number of splits:3
17/06/06 12:12:10 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1496761501347_0006
17/06/06 12:12:10 INFO impl.YarnClientImpl: Submitted application application_1496761501347_0006
17/06/06 12:12:10 INFO mapreduce.Job: The url to track the job: http://ip-172-31-16-37.eu-west-1.compute.internal:8088/proxy/application_1496761501347_0006/
17/06/06 12:12:10 INFO tools.DistCp: DistCp job-id: job_1496761501347_0006
17/06/06 12:12:10 INFO mapreduce.Job: Running job: job_1496761501347_0006
17/06/06 12:12:16 INFO mapreduce.Job: Job job_1496761501347_0006 running in uber mode : false
17/06/06 12:12:16 INFO mapreduce.Job:  map 0% reduce 0%
17/06/06 12:12:22 INFO mapreduce.Job:  map 33% reduce 0%
17/06/06 12:12:27 INFO mapreduce.Job:  map 100% reduce 0%
17/06/06 12:12:28 INFO mapreduce.Job: Job job_1496761501347_0006 completed successfully
17/06/06 12:12:28 INFO mapreduce.Job: Counters: 38
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=380445
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1762
		HDFS: Number of bytes written=500000000
		HDFS: Number of read operations=45
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=13
		WEBHDFS: Number of bytes read=500000000
		WEBHDFS: Number of bytes written=0
		WEBHDFS: Number of read operations=12
		WEBHDFS: Number of large read operations=0
		WEBHDFS: Number of write operations=0
	Job Counters
		Launched map tasks=3
		Other local map tasks=3
		Total time spent by all maps in occupied slots (ms)=23092
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=23092
		Total vcore-seconds taken by all map tasks=23092
		Total megabyte-seconds taken by all map tasks=23646208
	Map-Reduce Framework
		Map input records=4
		Map output records=0
		Input split bytes=342
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=153
		CPU time spent (ms)=18330
		Physical memory (bytes) snapshot=757821440
		Virtual memory (bytes) snapshot=4716625920
		Total committed heap usage (bytes)=1078984704
	File Input Format Counters
		Bytes Read=1420
	File Output Format Counters
		Bytes Written=0
	org.apache.hadoop.tools.mapred.CopyMapper$Counter
		BYTESCOPIED=500000000
		BYTESEXPECTED=500000000
		COPY=4
[hdfs@ip-172-31-29-116 ~]$ hdfs fsck /user/hdfs/teragen-leonceda -files -blocks
Connecting to namenode via http://ip-172-31-16-37.eu-west-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.29.116 for path /user/hdfs/teragen-leonceda at Tue Jun 06 12:13:22 EDT 2017
/user/hdfs/teragen-leonceda <dir>
/user/hdfs/teragen-leonceda/teragen-leonceda <dir>
/user/hdfs/teragen-leonceda/teragen-leonceda/_SUCCESS 0 bytes, 0 block(s):  OK

/user/hdfs/teragen-leonceda/teragen-leonceda/part-m-00000 250000000 bytes, 2 block(s):  OK
0. BP-1114411984-172.31.16.37-1496759340010:blk_1073742749_1925 len=134217728 Live_repl=3
1. BP-1114411984-172.31.16.37-1496759340010:blk_1073742752_1928 len=115782272 Live_repl=3

/user/hdfs/teragen-leonceda/teragen-leonceda/part-m-00001 250000000 bytes, 2 block(s):  OK
0. BP-1114411984-172.31.16.37-1496759340010:blk_1073742748_1924 len=134217728 Live_repl=3
1. BP-1114411984-172.31.16.37-1496759340010:blk_1073742751_1927 len=115782272 Live_repl=3

Status: HEALTHY
 Total size:	500000000 B
 Total dirs:	2
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	4 (avg. block size 125000000 B)
 Minimally replicated blocks:	4 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Tue Jun 06 12:13:22 EDT 2017 in 2 milliseconds


The filesystem under path '/user/hdfs/teragen-leonceda' is HEALTHY

```
