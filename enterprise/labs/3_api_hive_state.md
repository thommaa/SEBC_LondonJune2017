`curl -u thommaa:cloudera http://localhost:7180/api/v12/clusters/thommaa/services/hive`
```json
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-28-183.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_WEBHCATS_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : true
}
```
Stop the Hive services
`curl -X POST -u thommaa:cloudera http://localhost:7180/api/v12/clusters/thommaa/services/hive/commands/stop`
```json
{
  "id" : 592,
  "name" : "Stop",
  "startTime" : "2017-06-07T13:27:31.665Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

Start Hive services
`curl -X POST -u thommaa:cloudera http://localhost:7180/api/v12/clusters/thommaa/services/hive/commands/start`
```json
{
  "id" : 598,
  "name" : "Start",
  "startTime" : "2017-06-07T13:29:12.907Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
