# 4_Kubernetes-UpcominStorageFeatures


<!-- MarkdownTOC -->

- [0 - Overview](#0---overview)
- [1 - CSI](#1---csi)
- [2 - New things](#2---new-things)
  - [Volume Resizing](#volume-resizing)
  - [Topology awarness](#topology-awarness)
  - [LocalPVs](#localpvs)
  - [Snapshots](#snapshots)
  - [Inline Volumes](#inline-volumes)
  - [Namespace transfers of PVC](#namespace-transfers-of-pvc)
  - [Populators](#populators)

<!-- /MarkdownTOC -->



## 0 - Overview

Links:
- https://fosdem.org/2019/schedule/event/containers_k8s_storage/



## 1 - CSI

Make an effort to propose a common way to define storage usage in k8s



## 2 - New things

### Volume Resizing

Hot resizing


### Topology awarness

CSI Plugins deployed as CRD wull be able to define and be aware of node specificity


### LocalPVs

Targets 1.14


### Snapshots

- Alpha since 1.12
- External CRD
- More features (Group-snapshot, consistency checks, ...)


### Inline Volumes

- Volumes defined in Pod Spec
- Will be able to chose from persistent / ephemeral
- Not the PVC way


### Namespace transfers of PVC


### Populators

- Specify DataSources
- Allow to create PVC and put data in before containers gets attached to it
  + A Snapshot
  + External cloner
  + ...
- Under the hood, starts a k8s Job with all the definition given in the spec to poplate the pvc


