Report the latest available version of the API
`curl -u thommaa:cloudera http://localhost:7180/api/version`
For the CM 5.8.3 it returns
```
v13
```

Report the CM version
`curl -u thommaa:cloudera http://localhost:7180/api/v13/cm/version`
```json
{
  "version" : "5.8.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20161019-1014",
  "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
  "snapshot" : false
}
```

List all CM users
`curl -u thommaa:cloudera http://localhost:7180/api/v13/users`
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
`curl -u thommaa:cloudera http://localhost:7180/api/v13/cm/config`
Failed to identify the database configuration
