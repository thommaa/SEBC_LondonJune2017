```json
{
  "timestamp" : "2017-06-07T12:50:14.194Z",
  "clusters" : [ {
    "name" : "thommaa",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "1485832192"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "1485832192"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "1641755443"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "276"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-28-183.eu-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-2dc68a8d13164cd27446d72052206969",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0ba655331d200ba81"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-8d90a090af78a0e9a1374a579c41c979",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0afaab9f66365d81d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-9c205e8579945339fcf71bb1a26e2f40",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0b3ffee0546dd9ca9"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-9c95328de83ded506b23e1682c3a699f",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cqjbkpkeli1it66rxgmofoypg"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "56a40wqsv0i374qhsvrifedr6"
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "WEBHCAT",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_webhcat_secret_key",
            "value" : "mKkKbJBjyOV86E3j9WatVWzNJxbAU6"
          }, {
            "name" : "role_jceks_password",
            "value" : "cgmza30bwa9x7nrou7dq3x468"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "851443712"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-8d90a090af78a0e9a1374a579c41c979",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0afaab9f66365d81d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7neocxmwaus4w6mtm1ny9u8xg"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-9c95328de83ded506b23e1682c3a699f",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3x3xcul4rtop3euc40x8ggxuq"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7hcerivnnhdmfj4eij32gjk8p"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-28-183.eu-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "huepassword"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-2dc68a8d13164cd27446d72052206969"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-9c95328de83ded506b23e1682c3a699f",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "68urs7yhukmipprz1kkwoa9ej"
          }, {
            "name" : "secret_key",
            "value" : "4E1lCNfjuyRJcxxTfWloDQFgtVg2sa"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9uoyrihqlytccu9gmb6fldbca"
          }, {
            "name" : "secret_key",
            "value" : "z2MFBEucnkw0YvY1by3hbvRF0KAjt0"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-28-183.eu-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-9c95328de83ded506b23e1682c3a699f",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a7cu4bpkwcat3mu5p5c26s8ae"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "851443712"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "4194"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "851443712"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4630"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "ZAAUQZ7toBrWUuKau2uStgttapi22U"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-8d90a090af78a0e9a1374a579c41c979",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-0afaab9f66365d81d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3zzay16vtzoihby2m47pknses"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2dc68a8d13164cd27446d72052206969",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0ba655331d200ba81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6trqfcqude0fndadh01rq0jlb"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-9c205e8579945339fcf71bb1a26e2f40",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0b3ffee0546dd9ca9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "879z4eiuzisqrmwhj39u8a3e2"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-9c95328de83ded506b23e1682c3a699f",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "88xpas9bxp4mw8x2issa5f7xr"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dyuditk4p66ok9wvyqy8lcov7"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-8d90a090af78a0e9a1374a579c41c979",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-0afaab9f66365d81d"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "5o840gxv2x2rsmcxl9sv7vvfo"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "851443712"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10568836710"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "T2JZ0tmWQ17j5yJ8E3C3quzIuFPAWJ"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "84lOkqzGSvBcTV3aY3I4yFjGKlr9RU"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "5gNWEvY8ISUxcjBsdKHVHo3aWBzNN1"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-8d90a090af78a0e9a1374a579c41c979",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-0afaab9f66365d81d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-2dc68a8d13164cd27446d72052206969",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0ba655331d200ba81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7a97360onkcka4f5xqbale8lr"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-9c205e8579945339fcf71bb1a26e2f40",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0b3ffee0546dd9ca9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "fepwahk2oni6aam8c5ev13rv"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-9c95328de83ded506b23e1682c3a699f",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b6yvxdujz43zogjrbmh5qucsy"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6jvchdejzi56x8pk6dkk448hv"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-8d90a090af78a0e9a1374a579c41c979",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0afaab9f66365d81d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "68jtc7cnqo7mhnmwgqilxu8wb"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-9c95328de83ded506b23e1682c3a699f",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cnz3hmz8q5w6ut5tw1orm7cdc"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-2dc68a8d13164cd27446d72052206969",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-0ba655331d200ba81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "401wgrumlws86s25wy2tdav8h"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-9c95328de83ded506b23e1682c3a699f",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4s2apmdm79w4lyvycip06ohuk"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "66ezjedlcsvg5rfm3c15g4fnj"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-2dc68a8d13164cd27446d72052206969",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0ba655331d200ba81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4at7bk7vsmal5qoq3yi8lb67o"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-9c205e8579945339fcf71bb1a26e2f40",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0b3ffee0546dd9ca9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "czkrlf45qautyatri84w9d5rk"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-db2bb9b8ad2acdcc072f7c9ddb12dd54",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-00231b62d6a7213d3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7efx4rjnc121019c8rennzjta"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-8d90a090af78a0e9a1374a579c41c979",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0afaab9f66365d81d"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "59"
          }, {
            "name" : "role_jceks_password",
            "value" : "qpo6q2asjyb93ck729o87m92"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-9c95328de83ded506b23e1682c3a699f",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-09b582f45379fb9b4"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "65"
          }, {
            "name" : "role_jceks_password",
            "value" : "392nz11e1lsjyvage4njqn4og"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0afaab9f66365d81d",
    "ipAddress" : "172.31.16.37",
    "hostname" : "ip-172-31-16-37.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-09b582f45379fb9b4",
    "ipAddress" : "172.31.21.20",
    "hostname" : "ip-172-31-21-20.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-00231b62d6a7213d3",
    "ipAddress" : "172.31.24.30",
    "hostname" : "ip-172-31-24-30.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0ba655331d200ba81",
    "ipAddress" : "172.31.28.183",
    "hostname" : "ip-172-31-28-183.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0b3ffee0546dd9ca9",
    "ipAddress" : "172.31.29.116",
    "hostname" : "ip-172-31-29-116.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__7b3f6e99-b45d-48a5-beba-d0e84b2a09ae",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "40417267e6cb6f948afa000a493aad0b010a8d57ac24d00ab91ac8327b92e136",
    "pwSalt" : 7198472974800026660,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-8d90a090af78a0e9a1374a579c41c979",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3e3f53d4df1bc867256d6b5784f56b672378015755ec06c1b28d1b43f82c4606",
    "pwSalt" : 1793840059617657276,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-8d90a090af78a0e9a1374a579c41c979",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "2e1111008be8ed8e9cd7ed2befb0d0a71c470d19d000de5f6259bde606a2c79a",
    "pwSalt" : -8407189810099483143,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-8d90a090af78a0e9a1374a579c41c979",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0bb71a9c0eae191e76a34a3d7735829e15f59ac3a1fff16b8e0cd87d0f1a6283",
    "pwSalt" : -7578836936336093264,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-8d90a090af78a0e9a1374a579c41c979",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "f68ad246efcbf5dce355b4e8e4e5d9c6c968a23be1f21f9db8a399eed3d81864",
    "pwSalt" : 6430150223894334151,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "5550aee12d2da29de285a75cadc512d7dda9dc9e69ce1dcc5a764946315b9b4b",
    "pwSalt" : -5035617945626164509,
    "pwLogin" : true
  }, {
    "name" : "bdruser",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "5c0e0794956fd8c112790203b37cf37ce31a843f5161d86000ca96869926e468",
    "pwSalt" : 8945237069075431184,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "3132ff1decee6e07c29adcf309ac4bc621d0b751e60e59b0c20fd0f8ba232cf0",
    "pwSalt" : -8557364988551711901,
    "pwLogin" : true
  }, {
    "name" : "thommaa",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "d112d02e7044c82d2947c20773d9bbc4fea1a89b33ccebde09743fdd83fa036b",
    "pwSalt" : 2750638124562798797,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1014",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "851443712"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-28-183.eu-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "851443712"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-8d90a090af78a0e9a1374a579c41c979",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-0afaab9f66365d81d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5k8690dos3gwlpyajh7lm0hll"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-8d90a090af78a0e9a1374a579c41c979",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-0afaab9f66365d81d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "976twu1r19jbjqsvz4xopnvbg"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-8d90a090af78a0e9a1374a579c41c979",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-0afaab9f66365d81d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d63zc7nit1fxrtgc6i7b853l6"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-8d90a090af78a0e9a1374a579c41c979",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-0afaab9f66365d81d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d0hvhd7594f0iuqhfl5nosulz"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-8d90a090af78a0e9a1374a579c41c979",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-0afaab9f66365d81d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "brkquobd9moxr7dl11sgbnime"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/26/2012 2:00"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/,https://archive.cloudera.com/cdh5/parcels/5.8.3/,https://archive.cloudera.com/cdh5/parcels/latest/,https://archive.cloudera.com/cdh5/parcels/{latest_supported}/"
    } ]
  }
}
```
