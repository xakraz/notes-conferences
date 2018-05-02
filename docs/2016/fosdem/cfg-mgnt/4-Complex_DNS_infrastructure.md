4-Complex_DNS_infrastructure
----------------------------

<!-- MarkdownTOC -->

- [Intro](#intro)
- [Talk insight](#talk-insight)
- [Tools we use](#tools-we-use)
  - [Overview](#overview)
  - [Sparts](#sparts)
  - [Thrift](#thrift)
- [DNS](#dns)
  - [Tools](#tools)
  - [VIP Advertisement](#vip-advertisement)
  - [DNS modifications](#dns-modifications)
- [Content management (Auto / Human)](#content-management-auto--human)
  - [Auto generated](#auto-generated)
  - [Conflicts](#conflicts)
- [External DNS](#external-dns)
- [CCL](#ccl)
- [Question](#question)

<!-- /MarkdownTOC -->


https://fosdem.org/2016/schedule/event/managing_complex_dns_environment/



# Intro

* Speaker
  - Production Engineer, Cluster Infrastructure
  - Cluster life cycle / Provisioning (Add / remove capacity)
  - Manage
    + DNS, DHCP, TFTP, OS images ...

* What is a cluster
  - A group of machines that have the same "role" and serve the same service

* DNS entries
  - Servers
  - Services

* Managing DNS is NOT easy !




# Talk insight

* Not YAO cfgmngt talk
=> will talk about:
  - Microservices
  - Distributed system config (zookeeper)
  - Pipelines

* Building blocks
  - Mostly FOS
  - Python glue


# Tools we use

## Overview

* Baremetal: chef
* Container: LXC

* Service: "sparts"
  - Daemon
  - Generate Rules + execution
  - init or Runit for DNS daemons manager


## Sparts

* Boilerplate
* Common features
* Task, loggingm counters
* CLI fro free
* Subscribe on configuration updates
=> Facebook Github


## Thrift

* Allow us to build API for services
* Part of Apache
* 




# DNS

## Tools

* Structure:
  - TinyDNS:  Authority
  - Unboud:   Recurser

* TinyDNS
  - Configuration easier
  - Reliable, secure, simple
  - MAPs tweaked for our external LoadBalancer

* Unboud
  - Fast
  - Reliable,
  - Performance were good + Small memory foot print
  - Local cache


## VIP Advertisement

* BGP + ECMP
* ExaBGP to annince VIP
  - Easy Rollout :)


## DNS modifications

* Mostly automated
  - Servers ask register / deregister

* Config
  - TinyDNS + Unbound
  - 2 config files
  - Every servers has ALL the config

=> Configurator
  - Python DSL (Thrift interface for syntax, Python Config generator, Pyhton validator)
  - Generate JSON
  - Review process
  - Zookeeper and proxies
  - Local Proxy on server

* Configurator
  - Watch a configfile
  - Ensure it is upToDate



# Content management (Auto / Human)

## Auto generated

* Sparts + Rules
  - Rules = python classes
  - Generate DNS records
  - Streamed to Zookeeper

> Configuration is never Stale


## Conflicts

* "Presenter"
  - Sparts + Rules
  - Retrive config from Zookeeper and Human changes
  - Reconciliate

* Distribution
  - Bittorrent

* Data Pipeline
  - Human / Robot
  - Configurator / (DNS mutator + zk nodes)
  - Presenter
  - Publisher
  => Torrent file in ZK
  => Seed torrent

=> Internal DNS



# External DNS

* Billion users ?
  - Load balance
  - Recuce latency
  - ...

=> "points of presence"
  - Closer to users


* How redirect users ?
  - Measuring "Closeness"
  - Thanks to CDN and Uniq DNS name / users

=> Compute a MAP



# CCL

* Split complex services in simple services that you combine
* No state when possible
* Reliability / Reproducibility
=> Becomes easier to manage


# Question

* Config deployment ?
  - The torrent file is registred  into ZK
  - Thanks to the Local proxy we deploy the info
  - Bittorrent is the data transport mechanisme
  - Thirft is the interface to ...

* Pipeline / Monitoring
  - Monitor the TXT record timestamp

* Config files
  - All records for external IPs
  - All records for Internal IPs
  - All records for servers
  - Everything is synced accros the world




