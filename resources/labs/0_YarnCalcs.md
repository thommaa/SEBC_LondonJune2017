Adjustment of the OS memory consumption to 5% to hit about 6GB for OS
(as 4 - 8 GB are usually sufficient for the OS - depending on other services and agents running on the machine)

The workload factor is influenced by the usage of the cluster: eg.
* only compute cluster
* also data streaming (kafka or spark processing)
* data access expected or wanted on storage applications as HBase or Impala

So if the resources are purely for computation then a higher workload (usage of the resources) is possible. If additional service need to be provided from the cluster, than a value of 1 or 2 should be used. 
