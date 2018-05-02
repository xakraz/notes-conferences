5-CfgMgnt_and_containers
------------------------

<!-- MarkdownTOC -->

- [Cfg Mgnt](#cfg-mgnt)
  - [system management patterns](#system-management-patterns)
  - [Cfg mgnt solved problems](#cfg-mgnt-solved-problems)
  - [Emergent issues](#emergent-issues)
- [Containers](#containers)
  - [Overview](#overview)
  - [Benefits](#benefits)
- [Cfg mgnt & Containers](#cfg-mgnt--containers)
- [Delivery patterns](#delivery-patterns)
  - [Uncontained](#uncontained)
  - [Contained](#contained)

<!-- /MarkdownTOC -->


Speaker
  - Previously Chef
  - Worked with
    + Ansible
    + LXC / Docker
  - Now
    + Juju @canonical



# Cfg Mgnt

## system management patterns

* Divergence
  - SSH + Manual actions

* Convergence
  - Puppet / Chef
  - Continuously diverge and converge

* Congruence
  - State "does not change"


## Cfg mgnt solved problems

1. Stopped divergent delivery patterns
2. Eliminate snowflakes
3. Framework to describe a system state
4. Support existing ecosystem (Distro, pkgs)
5. Abstraction


## Emergent issues

1. Domain specific needs
2. Context sensitve knowledge
3. Does not solve people and organization issues



# Containers

## Overview

* New parradigm that are "confused" people

* 2 Flavors
  - Application containers
  - System containers


## Benefits

1. Easy resources constraints
2. Density
3. Fast
4. No overhead



# Cfg mgnt & Containers



# Delivery patterns

Case of study: Kubernetes deployment

## Uncontained

* Lots of LOC
* Required Build Env
* Differents model possible
* Difficult management of artifacts


## Contained

* No dedicated build env
* Delivery time reduced
* Same model than Google suggestion (Doc)




















