# vse-carslab-managed
A repository for deploying Openshift workload clusters from a hub cluster with ACM and Argo CD.  
All cluster workload lifecycle is managed by Argo CD, including Argo configuration itself.

## How to run it
```shell
oc apply -k components/applicationsets/
```

# Structure
|#|Directory Name|Description|
|---|----------------|-----------------|
| 1. | `components` | This is where all the ApplicationSets YAMLs live.|
| 2. | `clusters` | This is where the new clusters configuration is stored. <br /><br /> To add a new workload cluster, one needs to add a directory with some yaml in the `overlays` directory. See the `volante` directory as an example.|
