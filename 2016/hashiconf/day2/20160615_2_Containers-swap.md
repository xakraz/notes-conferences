20160615_2_Containers-swap
---------------------------

<!-- MarkdownTOC -->

- [Principles](#principles)
- [Bootstapping etcd](#bootstapping-etcd)

<!-- /MarkdownTOC -->


# Principles

Build OS images
- Testable
- Repeatable
- Faster to instantiate
- More reliable (Time to install packages, remote dependencies ...)

```
Tips:
* Use a "minimale" OS image
```


Cluster all the things
- No single point of failure


Bootstapping Etcd
- Discovery service ?
  + DONT depend on the Public service
  + Host your own private one
  => BUT still something to maintain ... while bootstrapping ?
- DNS
  + Too statics

=> Etcd bootstraping service:



# Bootstapping etcd

Shell script running on each CoreOS instance
- Relying on AWS Auto-scaling feature

```
* Determin if a cluster exists
  - query local ETCD running
* If not, start one
  - query AWS autoscaling group
  - get list of existings nodes
  - Wait till there are enough members to create a cluster
* Otherwhise, join
  - query AWS autoscaling group
  - get list of existings nodes
```

=> "External" Metadata store is the Key !!!



