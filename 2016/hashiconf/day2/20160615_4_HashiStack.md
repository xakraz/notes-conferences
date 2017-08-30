20160615_4_HashiStack
---------------------

<!-- MarkdownTOC -->

- [0 - Overview](#0---overview)
- [1 - Stack](#1---stack)
- [2 - Demo](#2---demo)
  - [2.0 - Initial State](#20---initial-state)
  - [2.1 - Vault config](#21---vault-config)
  - [2.2 - Nomad](#22---nomad)
    - [Job: HashiApp](#job-hashiapp)
    - [Job: Consul](#job-consul)
    - [Nomad scheduling](#nomad-scheduling)
  - [2.3 - Fabio](#23---fabio)
- [3 - Scale / Update](#3---scale--update)
- [4 - FAQ](#4---faq)
  - [4.1 - k8s / Nomad](#41---k8s--nomad)
  - [4.2 -](#42--)

<!-- /MarkdownTOC -->



# 0 - Overview

https://www.hashiconf.eu/talks/hyperscale-computing-with-grpc-and-the-hashiStack.html

>
> How to build an "hyperscale" applications from the ground up using the **HashiStack**
> * Nomad,
> * Vault,
> * and Consul
>




# 1 - Stack

1 Server:
- Consul
- Nomad
- Vault

4 Clients
- Consul
- Nomad

+ DNSMasq local to get `.consul` resolution




# 2 - Demo

## 2.0 - Initial State

* Consul UI, everything is OK
  - 3 Consul
  - 3 Nomad
  - 1 Vault

>
> `Vault` can auto-register to Nomad / Consul since `0.6.0`
>

```
$ nomad status

No job is running
```



## 2.1 - Vault config

Policy
- Secrets for the App:  Read, list
- Secrets for MySQL:    Read, list
- Token:                DONT forget to add an "update" policy for `renew`

>
> It is the responsability of the App to renew Token when needed
>



## 2.2 - Nomad

### Job: HashiApp

```
Job names

Update          // For deployment

Group           // For Clustering

Task "HashiApp"
- Driver = exec
- Env with VAULT tokens
- Artifact

Resources       // For Nomad Scheduler
- CPU
- Memory
- Network

Service         // For Consul registering
- Name
- Tags
- Checks
- ...

```


### Job: Consul

A SYSTEM job definition to have a `Consul` agent running on EVERY Nomad workers


### Nomad scheduling

```
$ nomad plan job/consul.job


$ nomad run job/consul.job
```



## 2.3 - Fabio

Fabio desc:
* A loadbalancer / router
* Integrated with Consul
  - Use services
  - Tags
  - ...

Fabio usage:
* Nomad SYSTEM job
* Binded to local consul
=> Every Fabio instances see the same things




# 3 - Scale / Update

1. Update Job
2. `$ nomad plan`
3. `$ nomad run`

What happens:
- Nomad:
  + Services are started
  + Registered in Consul
- Consul
  + Do Health checks
  + check pass greens
  + Services are in Consul catalog
- Fabio
  + list Services




# 4 - FAQ

## 4.1 - k8s / Nomad

HashiTools are good pieces
k8s is a platform manager

=> We are looking to integrate `Vault` + `Nomad` (Scheduling) into k8s


## 4.2 -



