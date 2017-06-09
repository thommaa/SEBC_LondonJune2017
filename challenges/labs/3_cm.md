# creation of hdfs folders for theresa and jeremy
```bash
sudo su - hdfs
hdfs dfs -mkdir /user/theresa
hdfs dfs -mkdir /user/jeremy
```

# listing of folders
```
sudo su - hdfs
hdfs dfs -ls /user
```
Result
```

```


# API call
```
curl -u admin:admin http://localhost:7180/api/v14/hosts
```
Result
```json
{
  "items" : [ {
    "hostId" : "1302e620-58a1-482a-9b3d-9310d8ef9ad6",
    "ipAddress" : "172.31.33.176",
    "hostname" : "ip-172-31-33-176.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-34-150.eu-west-1.compute.internal:7180/cmf/hostRedirect/1302e620-58a1-482a-9b3d-9310d8ef9ad6",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15799816192
  }, {
    "hostId" : "352ac68a-6766-4116-93ac-bffd0c717ff7",
    "ipAddress" : "172.31.33.70",
    "hostname" : "ip-172-31-33-70.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-34-150.eu-west-1.compute.internal:7180/cmf/hostRedirect/352ac68a-6766-4116-93ac-bffd0c717ff7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15799816192
  }, {
    "hostId" : "c1ce0ca2-455b-47e3-9bf3-fccf6cf850c2",
    "ipAddress" : "172.31.34.150",
    "hostname" : "ip-172-31-34-150.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-34-150.eu-west-1.compute.internal:7180/cmf/hostRedirect/c1ce0ca2-455b-47e3-9bf3-fccf6cf850c2",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15799816192
  }, {
    "hostId" : "2469b2f7-57d5-4014-890a-9fb8ee332680",
    "ipAddress" : "172.31.40.167",
    "hostname" : "ip-172-31-40-167.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-34-150.eu-west-1.compute.internal:7180/cmf/hostRedirect/2469b2f7-57d5-4014-890a-9fb8ee332680",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15799816192
  }, {
    "hostId" : "c806b986-bf6e-4821-b0f2-781cf6bef2a3",
    "ipAddress" : "172.31.44.94",
    "hostname" : "ip-172-31-44-94.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-34-150.eu-west-1.compute.internal:7180/cmf/hostRedirect/c806b986-bf6e-4821-b0f2-781cf6bef2a3",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15799816192
  } ]
}
```
