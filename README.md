# vse-carslab-managed

Given the GitOps methodology and conventions agreed for the three kinds of identified workload clusters (SNO, SNO SiteConfig and Compact cluster), this repo will act as source of truth for SNO, SNO SiteConfig, and Compact (3-node) workload clusters custom configurations in cars.lab environment.

Note that the provisioning of custom configurations of interest (e.g., sriov operator, ptp, etc) on a given workload cluster starts `AFTER` a fresh base workload cluster is installed from hub cluster. 


## How to run it
```shell
oc apply -k bootstrap/applicationsets
```

# Structure
|#|Directory Name|Description|
|----|--------------|-----------------|
| 1. | `bootstrap`  |  Minimal YAML files to bootstrap custom configuration. <br /> Usually an argoCD appset that loads the required components in a fresh-installed workload cluster.|
| 2. | `components` | This is where all the application and pipelines bases YAMLs for workload cluster live.|
| 3. | `clusters` | This is where the cluster configuration overlays go. <br />To add a new workload cluster custom config, one needs to add a directory with some yaml in the `overlays` directory. <br /> See the `volante` directory as an example.|
