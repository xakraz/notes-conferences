20160614_Nomad-ClusterScheduler
--------------------------------


<!-- MarkdownTOC -->

- [0 - Intro](#0---intro)
  - [0.1 - Overview](#01---overview)
  - [0.2 - Role of Scheduler](#02---role-of-scheduler)
  - [0.3 - Nomad](#03---nomad)
  - [0.4 - Nomad job](#04---nomad-job)
  - [0.5 - Data model](#05---data-model)
    - [0.5.1 - Evaluation](#051---evaluation)
    - [0.5.2 - Allocation](#052---allocation)
- [1 - Fault tolerence](#1---fault-tolerence)
- [2 - Traffic shaping](#2---traffic-shaping)
- [3 - Ops insights](#3---ops-insights)
- [4 - Delivery + Scheduling](#4---delivery--scheduling)
    - [Scheduling \(server side\)](#scheduling-server-side)
    - [Client side](#client-side)
- [5 - Scale system administrations](#5---scale-system-administrations)
- [6 - Resource utilization](#6---resource-utilization)
- [CCL](#ccl)

<!-- /MarkdownTOC -->



# 0 - Intro

## 0.1 - Overview

Speaker
- Several start-ups before
- Comes from Netflix
- Works on Nomad @Hashicorp
  + Tested several stuff (Mesos on AWS)


WebOps


Netflix
- Already a really good deployment tool
- But still 15min to create a cluster


## 0.2 - Role of Scheduler

1. Improve Fault tolerence
2. Aid traffic shaping accross DC and geographies
3. Operation insights
4. Uniform deployment
5. Scale system administration and operations
6. Increase resource utilization


## 0.3 - Nomad

Distributed cluster scheduler
- Multi DC based
- Multi region support
- Flexible workload
- Job priorities
- Bin packing
- Large scale
- Ops simple

Others:
- Inspired by Google Omega
- Optimistic concurrency
- State coordination built-in (no external dependencies like Zookeeper, Etcd, Consul)
- Pluggable

Built-on top of
- Gossip (Serf)
- Consensus (Raft from Consul)

=> Built on Experience


## 0.4 - Nomad job

HCL (Json like)


## 0.5 - Data model

1. Evaluation
2. Allocation
3. Execution


### 0.5.1 - Evaluation

Can produces a lot of allocation requests

Type of Jobs
- Service
- Batch
- System


### 0.5.2 - Allocation

Current state of the system





# 1 - Fault tolerence

Should be the core goal of a scheduler

Types of failures:
* Recoverable failures
* Driver errors
* Scheduler failures



# 2 - Traffic shaping

States:
* Multi-DC are the new normal
* Active ~ Active accross regions needs for reliability
* Cluster have to be resizable
* Needs for 1 Control Pane for all


With Nomad
* 1 same jobfile can target multiple DC (Awarness)
* Unified interface for clouds
* ...



# 3 - Ops insights

Should:

* Help troubleshooting quickly and easily
  - Status
  - Events of a task

* Logs management
  - Rotation
  - Streaming to cliens
  - Forward to remote sink

* FS inspections
  - Inspect FS of a task

* Ops runtime metrics
  - Resources usage (Tasks, nodess, schedulers)
  - Forward to remote sink



# 4 - Delivery + Scheduling

Uniform delivery semantic
- Support for various DRIVERS
Smart rolling updates
Job priotiries
Concurrent scheduling


### Scheduling (server side)

Concurrent + Optimistic
- Evaluation -> Broker -> Scheduluer (PLAN)-> aAllocation
- PLAN


### Client side

Broad OS support
Host fingerprint
Pluggable drivers



# 5 - Scale system administrations

xxx
- ...

System jobs
- Run on every nodes
- Greate for INFRA / Monitoring / Logging auditing software

Maintainance primitives
- Drain allocations from 1 node to an other

Nodes / worker status



# 6 - Resource utilization

Bin packing
Blocked evaluation if no more resources
API for cluster usage querying (COMMING)



# CCL

Benchmark to PUSH nomad
-> 1.000.000 Containers
-> Scheduled, allocated, Started < 300s

Comming soon
* Features
  - Persistent volumes
  - Networking
  - ACLs
  - Premption
* Integration
  - Vault
  - Auto-scaling
  - Charge-back

