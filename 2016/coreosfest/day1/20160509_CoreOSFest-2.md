20160509_CoreOSFest-2
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
  - [Weave](#weave)
  - [Weave topology](#weave-topology)
  - [Raft](#raft)
- [2 - Add ETCD for discovery](#2---add-etcd-for-discovery)
  - [ETCD](#etcd)
  - [Gossip / Raft implementation](#gossip--raft-implementation)

<!-- /MarkdownTOC -->


EtcD over gossip protocol



# 1 - Intro

## Weave

Weave networks for containers
- Docker initialy
- CNI plugin for Kube / DCOS



## Weave topology

* Router
* Meshed network
* Gossip Layer (between routers)
  - Receiver
  - sender
* Your application
  - Talks to the Gossip Communication protocol



## Raft

Raft is a *Consensus* protocol



# 2 - Add ETCD for discovery

## ETCD

Expected Stack:
1. API
2. "Mechanical Bits"
3. Storage
4. "Propose Layer"
5. Raft
6. Transport


Reality:
- Not clearly decoupled
- Not easy programable API
-> Will have to reimplment a Raft server node ...


## Gossip / Raft implementation

> In ETCD:
> * Raft "nodes" are supposed persistant
> * Raft "nodes" are identified
> 
> Wants "Ephemeral" behavior
> -> Implement **new NodeName ID** as UUID **at start-up**
> 



