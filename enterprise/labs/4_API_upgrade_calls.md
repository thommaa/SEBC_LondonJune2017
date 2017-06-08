Report the latest available version of the API
`curl -u thommaa:cloudera http://localhost:7180/api/version`
```
v14
```

Report the CM version
`curl -u thommaa:cloudera http://localhost:7180/api/v14/cm/version`
```json
{
  "version" : "5.9.2",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170330-1814",
  "gitHash" : "822da28bff818f57fc1bfc3eafe3a550300ef1b0",
  "snapshot" : false
}
```

List all CM users
`curl -u thommaa:cloudera http://localhost:7180/api/v14/users`
```json
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "bdruser",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "thommaa",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```

Report the database server in use by CM
**Wrong lead** -> Get all the roles for CM:
`curl -u thommaa:cloudera http://localhost:7180/api/v14/cm/service/roles | grep "type" -B1 | grep "name"`
Grab the names of the roles and pick the config here:
```
"name" : "mgmt-REPORTSMANAGER-8d90a090af78a0e9a1374a579c41c979",
"name" : "mgmt-ALERTPUBLISHER-8d90a090af78a0e9a1374a579c41c979",
"name" : "mgmt-HOSTMONITOR-8d90a090af78a0e9a1374a579c41c979",
"name" : "mgmt-SERVICEMONITOR-8d90a090af78a0e9a1374a579c41c979",
"name" : "mgmt-EVENTSERVER-8d90a090af78a0e9a1374a579c41c979",
```

`for role in $(curl -u thommaa:cloudera http://localhost:7180/api/v14/cm/service/roles | grep "type" -B1 | grep "name" | sed 's/name//' | sed 's/[: ,"]//g'); do echo $role; curl -u thommaa:cloudera http://localhost:7180/api/v14/cm/service/roles/$role/config; done`

Basic information
`curl -u thommaa:cloudera http://localhost:7180/api/v14/cm/scmDbInfo`
```json
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```
