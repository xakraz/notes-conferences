20160510_Coreosfest_notes-1
---------------------------

<!-- MarkdownTOC -->

- [1 - coreos-baremetal](#1---coreos-baremetal)
  - [Overview](#overview)
  - [coreos-baremetal/bootcfg](#coreos-baremetalbootcfg)
  - [Network Environment setup](#network-environment-setup)
- [2 - Tests](#2---tests)
  - [Infra setup](#infra-setup)
  - [Bootcfg API](#bootcfg-api)

<!-- /MarkdownTOC -->



CoreOS Bootstraping



# 1 - coreos-baremetal

## Overview

https://github.com/coreos/coreos-baremetal

Coreos-baremetal:
* Guides
* 1 service (`bootcfg`)

`bootcfg`:
* Network boot config
* Provisioning CoreOS clusters
* Metadata


## coreos-baremetal/bootcfg

https://github.com/coreos/coreos-baremetal/blob/master/Documentation/bootcfg.md

HTTP server
* iPXE scripts (Kernel + Initrd)
* Ignitions / cloud-config config files (Bootstraping)
* Metadata / Logic


```
/var/lib/bootcfg/
 |
 ├── assets/
 |   └── coreos
 |        └── VERSION
 |            ├── coreos_production_pxe.vmlinuz
 |            └── coreos_production_pxe_image.cpio.gz
 |
 |
 |   // Network boot config
 ├── groups/
 │   └── default.json
 │   └── node1.json
 │   └── us-central1-a.json
 |
 └── profiles/
 │   └── etcd.json
 │   └── worker.json
 |
 |
 |   // CoreOS Config specific
 ├── cloud
 │   ├── cloud.yaml
 │   └── worker.sh
 └── ignition
     └── hello.json
     └── etcd.yaml
     └── simple_networking.yaml
```


* Groups
  - 1 Profile
  - 1 **Selector** (HW / Metadata logics)
  - Metadata associated for Profile templating

* Profil
  - Ignition / cloud-config
  - Network BOOT args (iPXE)


## Network Environment setup

* NO DHCP
* NO TFTP

=> Use DNSMasq




# 2 - Tests

## Infra setup

* 1 CoreOS VM
  - BootCFG HTTP servers
  - Dnsmasq DHCP/TFTP server

* 1 VBox VM PXE Boot



## Bootcfg API

https://github.com/coreos/coreos-baremetal/blob/master/Documentation/api.md

=> Allow to validate each part of Bootcfg
  * ipxe / ipxe script
  * Ignition Config
  * Metadata
  * Images






