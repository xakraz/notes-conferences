1-Beyond_cfg_mgnt
-----------------


<!-- MarkdownTOC -->

- [History](#history)
  - [1](#1)
  - [2](#2)
  - [3](#3)
- [New era](#new-era)
  - [1](#1-1)
  - [2](#2-1)

<!-- /MarkdownTOC -->


# History

## 1

* Main frames
* Servers pizza box
* VMs
* Containers

Mooving through paradigm
=> To solve issues, we build tools


## 2

* Provision the OS
* Configure the software
  1. SSH in a for loop
  2. CFG mgnt (agent)


Tools list
- cdist
- isconf
- lcfg
- pikt


## 3

* Everything new is supplementary
=> They DO NOT REPLACE previous tools
=> They are built "on" them to solve NEW issues that have been raised and we did not even reach before



# New era

## 1 

* Phase change of modern software
  - We add "layers" of abstration during the phase of build / installation / management

* What does it mean ?
  - "Modelling" is the next step

* Modelling is NOT:
  - Orchestration, is "encapsulation" of business rules & logic


## 2 

* Modelling as a "langage"
  - Machine:      Constrained resource
  - Applications: Definition of the lifecycle of a "service"
  - Units:        An implementation of an application
  - Scale:        Number of units
  - Relations:    How application communicate with each other
  
  Things that are still left over...
  - Resources
  - storage
  - Network

* Modeling should be Agnostic
=> Modeling + configuration management

* Modeling is description





