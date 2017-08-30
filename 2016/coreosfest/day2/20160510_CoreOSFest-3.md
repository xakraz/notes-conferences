20160510_CoreOSFest-3
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
  - [Fleet](#fleet)
  - [Giant-swarm](#giant-swarm)
  - [Limitations of Fleet](#limitations-of-fleet)
- [2 - Why still fleet?](#2---why-still-fleet)
- [3 - What is next?](#3---what-is-next)
  - [Ideas](#ideas)
  - [gRPC](#grpc)
  - [New Architecture](#new-architecture)
  - [Rolling updates](#rolling-updates)
- [4 - Benefits](#4---benefits)
- [5 - Validation](#5---validation)
- [6 - Future](#6---future)

<!-- /MarkdownTOC -->


Fleet improvement with gRPC



# 1 - Intro

## Fleet

Fleet: "Distributed Init System"
- Leverage SystemD units
- Use ETCD as distributed system

Fleet:
- `fleetd`: Daemon runningon every nodes, watching etcd
- `fleetctl`: Client cli to submit units


## Giant-swarm

* 1 Services.json main ail
* Each servies used several Units



## Limitations of Fleet

* Performances (due to ETCD)
* Fleet "out of sync"
  - Some agents are unresponsive
  - Some agents are incoherents

=> Limit of Scalability


Limit of FAIL
- If `etcd` goes down, eveything falls appart...



# 2 - Why still fleet?

* Simple
* Intuitive usage of `systemd`


=> Fleet helps to control basic blocs of infrastructure
  - Kubernetes / Mesos components
  - Others stuff that do not have complex workflows, lifecycle



# 3 - What is next?

## Ideas

* Reduce etcd dependencies
* Better perf
* Improve failures recovery
* Mitigate scalability issues


## gRPC

* gRPC is now used as communication layer between `fleetd`
* `etcd` is used only for storage
=> Perf and dependencies


## New Architecture

Fleetd Engine
- "Servers" mode
- Only "master" talks to etcd

Fleetd agents
- talks to Engines cluster via gRPC


## Rolling updates

* Engine/Agents detec if there are `etcd` nodes in the cluster
* Implement "Lock" mechanism on etcd



# 4 - Benefits




# 5 - Validation

Config
* 3 nodes Engines cluster
* 4 nodes Agents cluster

Scenario
1. 3k units comparison `fleet-etcd` / `fleet-grpc`
2. Fleet vs systemd (interaction)
3.

> Notes
> --
>
> Systemd *units linking* is very EXPENSIVE
>

+ Performance improvements



# 6 - Future

* etcd v3
* TLS
* Improve **state transition** of units
* Change **Reconciliation loop** mechanism




