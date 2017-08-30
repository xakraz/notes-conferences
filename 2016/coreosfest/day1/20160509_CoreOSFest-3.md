20160509_CoreOSFest-3
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
- [2 - Docker & Rkt](#2---docker--rkt)
  - [Docker daemon](#docker-daemon)
  - [Rkt for Platform builder](#rkt-for-platform-builder)
- [3 - Rkt in practice](#3---rkt-in-practice)

<!-- /MarkdownTOC -->


Rkt for Platform builders



# 1 - Intro

* PODs
* AppC
* OCI
* ...



# 2 - Docker & Rkt

* Rkt does NOT have a daemon
-> leave this to the Host INIT system mgnt (SystemD mainly)


## Docker daemon

* Daemon is a great **user** experience
* BUT
  - lack of composability
    + Host integration for process mgnt, Unikernel, networking
    + OK if you use the whole ecosystem (Compose, swarm, ...)
  - Process / Container MGNT especially (Restart Docker daemon -> Restart all containers)


## Rkt for Platform builder

* Unix philosophiy (Composable)
* Do not need ROOT permission



# 3 - Rkt in practice

* Rkt is a Container runtime, NOT imnage **builder** -> Use `ACbuild` tools

* **Run** container:
  - RKT implement several **Stages1**
  - Default is `systemd-nspawn`
  -> Logs access is done via `machinectl` / `journalctl`

* Rkt can run container from **Docker**:
  - `docker2aci` tool
  - Default "Squash" layers

* **Images** discovery + Distribution:
  - APPC specs (HTTP + HTML Meta Tags)


```shell

$ curl -sL https://quay.io/coreos/etcd | grep meta | grep discovery

  <meta name="ac-discovery" content="quay.io https://quay.io/c1/aci/{name}/{version}/{ext}/{os}/{arch}/">
  <meta name="ac-discovery-pubkeys" content="quay.io https://quay.io/aci-signing-key">

```


* PODs
  - Popularized by k8s
  - Collection of multiple Images sharing SOME namespaces
  - Default (Network, FS, IPC)

```
$ sudo rkt list

UUID App Image Name State CREATED STARTED NETWORKS
...
```

> Comments
> --
> 
> POD
> - 1 UUID
> - Multiple App listed
> 


