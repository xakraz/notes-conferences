20160510_CoreOSFest-5
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
- [2 - 'Mgnt' tool](#2---mgnt-tool)
  - [Design](#design)
- [3 - Notes](#3---notes)
  - [Events](#events)
  - [Distributed](#distributed)
  - [Auto-dependencies](#auto-dependencies)
- [4 - Demo](#4---demo)
  - [Auto-clustering](#auto-clustering)
  - [Real-time updates](#real-time-updates)
- [5 - Future](#5---future)

<!-- /MarkdownTOC -->



NextGen Config Mgnt



# 1 - Intro

https://github.com/purpleidea

Hacked a lot around Puppet
* Recursion
* Timers
* State machine

But HACKY



# 2 - 'Mgnt' tool

## Design

1. Parallel
2. Event driven
3. Distributed



# 3 - Notes

## Events

* Hooks with iNotify
* Hooks with SystemD


## Distributed

* Based on ETCD for shared / exported resources


## Auto-dependencies

* Available to leverage OS packages Mgnt to find dependencies



# 4 - Demo

## Auto-clustering

>
> "True" elastic cluter mgnt
>  - Can start additionnal member that won't be part of the cluster IF max_peers already reached
>  - If 1 peer leave, the next candidate will join
>


## Real-time updates

Thanks to Events



# 5 - Future

* DSL
* Resources
* ...


