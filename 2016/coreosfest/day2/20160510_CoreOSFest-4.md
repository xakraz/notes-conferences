20160510_CoreOSFest-4
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
  - [Phase 0](#phase-0)
  - [Phase 1](#phase-1)
  - [Phase 2](#phase-2)
  - [Phase 3](#phase-3)
- [2 - Dockyard](#2---dockyard)

<!-- /MarkdownTOC -->



Dockyard - Container Registry And Volume Management For rkt



# 1 - Intro

## Phase 0

Docker
* Leveraged LXC
* Avantages:
  - REST API
  - **Registry**
  - AUFS

=> Great UX
=> Greate User adoption


Docker Registry
* v1
  - Index + resgistry


## Phase 1

Rkt + ACI
* Advanced concepts of container and decoupling, composability
* Advanced concepts of containers images formats


## Phase 2

Docker Registry v2
* Index + Image stockage
* + **Authorization service**


## Phase 3

OCI initiative



# 2 - Dockyard

https://github.com/containersops/dockyard

Generic registry for both world
* Docker / Rkt ACI
* HTTP(s) / BitTorrent distributions support


\+ Built-in Object Storage service



