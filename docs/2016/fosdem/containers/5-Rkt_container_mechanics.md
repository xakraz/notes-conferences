5-rkt_container_mechanics
--------------------------


<!-- MarkdownTOC -->

- [Intro](#intro)
  - [CLI tool](#cli-tool)
  - [Stages](#stages)
- [Containers on Linux](#containers-on-linux)
  - [Namespaces](#namespaces)
  - [Cgroups](#cgroups)
- [Questions](#questions)

<!-- /MarkdownTOC -->


Speaker: Alban Crequy kinvolk.io


# Intro

What is `rkt` ?
* CLI tool
* Go
* Self contained


## CLI tool

* No daemon
* Fetch Images
* Start container
* Give the hand to the OS system process manager (SystemD on CoreOS)


## Stages

* 0
  - Discover/manage images

* 1
  - Manage POD, THE "container"
  - Handle multiple Process / App that have to run together as a "unit"
  - Get the dependencies / resources allocation requirements and constraints

>  Notes
>  --
>  
>  2 implementations of stage 1 nowadays
>  * systemd-nspaawn
>  * KVM
> 

* 2
  - The process that compose the container



# Containers on Linux

## Namespaces

* Views of a system
  - Mount
  - Hostname
  - ...

* Network support for `rkt`
  - "Plugin" based on CNI: Container Networking Interface (From the Appc project)
  - Support HOST only network
  - Supported plan from Kubernetes, Calico...

* Goals
  - Isolation

* Next
  - UserID namespaces
  - Allow Root that are not root :)


## Cgroups



# Questions
















