* What is ubertask optimization?
  * ubertask optimization runs "sufficiently small" jobs sequentially within a single JVM - depending on "Small" defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.
* Where in CM is the Kerberos Security Realm value displayed?
  * Under Administration - Settings - Kerberos filter group
  `<CM_Host>/cmf/settings#filterdisplayGroup=Kerberos`
* Which CDH service(s) host a property for enabling Kerberos authentication?
  * hdfs
  * mapred
  * yarn
  * oozie
  * hue
* How do you upgrade the CM agents?
  * updating the repository file and then the packages
  * or upgrade wizard that is invoked when you connect to the Admin Console (after update)
* Give the `tsquery` statement used to chart Hue's CPU utilization?
  * `select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=Hue`
* Name all the roles that make up the Hive service
  * HIVEMETASTORE
  * HIVESERVER2
  * hive-GATEWAY
  * hive-WEBHCAT
* What steps must be completed before integrating Cloudera Manager with Kerberos?
  * services must be stopped
  * configuration and services must be green before stopping
