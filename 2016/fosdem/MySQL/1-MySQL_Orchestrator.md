1-MySQL_Orchestrator
--------------------

Orchestrator: Smart MySQL Replication management

<!-- MarkdownTOC -->

- [Features](#features)
- [Summary](#summary)
- [Notes](#notes)

<!-- /MarkdownTOC -->


# Features

* Built from real-world use cases


* Support multi-layer Master/Slave replication topology
  - Topology discovery from 1 server


* Failure detection Euristic approch	
	- Ask each member of the cluster to get a full pictures
		+ Show slave status / show masterstatus

> Allow to support network split issue
>   - If orchestrator can not connect to 1 server, it may be a network issue
>   => Ask other servers of the cluster to make the descision


* Recovery + Promotion
  - By talking to each server: Can know which is the less late to promote
  - DC aware
  - Admin weight



# Summary

* Supported
  - Multi-DC
  - Various GTID flavour
  - Flapping behavior (Ack, manual, downtiming)
  - Various combination of flavour and usecases

* Limitation
  - MySQL Master/slave only (not galera)
  - Service discovery Hook support
  - Multi-source replication (Not yet)



# Notes

* Orchestrator is HA
  - HTTP Proxy + services / leader
  - MySAL Proxy + MySAL backends

* Very accurate
  - Detection < 20s
  - Recover before Nagios detection
  - ALOT (??)


* Used in production
  - Outbrains
  - Booking
  - Github
  - Sqare
  - BigDaddy
  - books





