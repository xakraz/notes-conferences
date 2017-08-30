20160509_CoreOSFest-4
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
  - [Rkt approach](#rkt-approach)
  - [Inside](#inside)
  - [Composability](#composability)
- [2 - Standards](#2---standards)
  - [OCI](#oci)
  - [CNI](#cni)
- [3 - K8s](#3---k8s)
  - [Overview](#overview)
  - [Insides](#insides)
- [4 - Rktnetes](#4---rktnetes)
  - [Pb](#pb)
  - [Docker 1.11](#docker-111)
  - [Rktnetes](#rktnetes)
- [5 - Next](#5---next)

<!-- /MarkdownTOC -->


Rktnetes: Support updates



# 1 - Intro

## Rkt approach

Security at core
	- UX verify images signature
	- UX verify images integrity

Unix philosophy
	- Well defined operations
	- No central privilieges


## Inside

Linux tech inside
- User namespace (euid Mapping)
- SELinux

Soon:
- Capabilities
- Seccomps
- Cgroups2
- Unprivileged containers


## Composability

"External" composability for integration
-> Simple command progra

"Internal" composability
- Stage0: Rkt API
- Stage1: POD abstraction
- Stage2: Container engine

Stage1s
- Cgroups + Linux namespaces
- LKVM
- Chroot ("fly")
- QEMU (soon)


> Comments
> --
> 
> "Fly" is especially usefull if you want to **use RKT as a pkg manager** (for CoreOS by example and just run a process) at host level
> 



# 2 - Standards

RKT emerged from need of standars, not depending of 1 Technology

1. Appc well defined SPEC for images
2. OCI
3. CNF
4. CNI


## OCI

Rkt is going to support OCI soon


## CNI

Has been widely adopted



# 3 - K8s

## Overview

Cluster-level container orchestration

* Today = Docker containers

> Comments
> --
> 
> K8s expose the PODs API
> -> No reason to be limited to docker
> 


## Insides

* Kublet is a daeons on every worker node
* Respond to deployment requests
* Give everything to the container engine

```
SyncPod()
GetPod()
RunPod()
...
```


# 4 - Rktnetes

* Pre: Kublet talks to Docker daemon API

## Pb

* Docker does not understand PODs natively
  - Workaround with "Infra container" to hold namespace for POD
* DockerD is a SPOF
  - Daemon stop, every container stops
* Docker does not integrat with SystemD (Cgroup mgnt)


## Docker 1.11

DockerD + ContainerD
* ContainerD runs and Manage the containers
* DockerD is still a daemon managing Images and API interface

> Comments
> --
> 
> Good start, but `cotnainerd` is still a SPOF at the time
> 



## Rktnetes

Kublet + Rkt:
* POD Native concept
* Integration with SystemD of Host
* POD process model (No SPOF)

Stack (Current):
* Kublet: Main entry point
* SystemD: For launching containers
* Rkt (API service) for quering managing running containers

Next ?
* Kubelet + Rkt without SystemD direct interaction


Should be released in k8s 1.2 late June



# 5 - Next

* K8s want to be able to update / modify a runing pod (Add / Remove container from POD)
* Leveraging POD concept to systemD
* OCI
  - `octool`