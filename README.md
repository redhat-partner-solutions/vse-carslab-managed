# vse-carslab-managed

Given the GitOps methodology and conventions agreed for the three kinds of identified workload clusters (SNO, SNO SiteConfig and Compact cluster), this repo will act as source of truth for SNO, SNO SiteConfig, and Compact (3-node) workload clusters custom configurations in cars.lab environment.

Note that the provisioning of custom configurations of interest (e.g., sriov operator, ptp, etc) on a given workload cluster starts `AFTER` a fresh base workload cluster is installed from hub cluster. 


# Structure
|#|Directory Name|Description|
|----|--------------|-----------------|
| 1. | `clusters` | This is where the cluster post-install configuration overlays go. <br />To add a new workload cluster custom config, one needs to add a directory with some yaml in the `overlays` directory. <br /> See the `clusters/overlays/volante` directory as an example.|

## How to run a post-install configuration

To run a post-install configuration in cluster volante:
```
until oc apply -k https://github.com/redhat-partner-solutions/clusters/vse-carslab-managed/overlays/volante; do sleep 3; done
```
