20160615_6_Consul-LoveStory
---------------------------


<!-- MarkdownTOC -->

- [1 - Ideal Operator workflow](#1---ideal-operator-workflow)
- [2 - Before](#2---before)
  - [Tech stack](#tech-stack)
  - [Constat](#constat)
  - [Feeling](#feeling)
- [3 - New](#3---new)
  - [3.1 - Replace Chef](#31---replace-chef)
  - [3.2 - Replace Munin](#32---replace-munin)
  - [3.3 - Replace HAproxy](#33---replace-haproxy)
  - [3.4 - Monitoring / Alerts](#34---monitoring--alerts)
- [4 - Ccl](#4---ccl)
- [5 - Demos](#5---demos)
- [6 - Next](#6---next)

<!-- /MarkdownTOC -->




# 1 - Ideal Operator workflow


# 2 - Before

@Bondary

## Tech stack

* Chef provisionning
* Munin Metrics

* 32 Services
* 3 Instances of each
* Haproxy fanout


## Constat

CFG mgnt was 75% of product's code base ...


## Feeling

"Cfg mgnt is a delivery vehicule for unfinished work"
- Like connecting dots ...
- Sucks but is sustainable

UNTIL
- Pivot to merge software stacks
- People leaves
- Saas, but sometime 1 client want premise
  + Need bootstrapping capabilities



# 3 - New

## 3.1 - Replace Chef

Replaced by :
- Serf (no server)
- little tool `cascade .5`  (hone made)

=> SUCCESS
=> Less painfull
=> More suitable for our needs


## 3.2 - Replace Munin

Remove active checks
GO passive checks
=> Sensu


## 3.3 - Replace HAproxy

By Consul

Reservation
- We already have ZK
- No NODE tags
- Events over Serf ?

Selling points
- ZK overloaded by Kafka
- Nice API
- Nice Patterns and usability
- Nice langage clients
- Semantic for service discovery

=> Remove Haproxy by Nginx


## 3.4 - Monitoring / Alerts

Checks are now in Consul
-> Agregate checks and make actionnable
-> `consul-alerts` Opensource tool



# 4 - Ccl

- Cfg is minimal
- Bootstrap = Create Node + install packages
- Sustainable (service registering + Monitoring)



# 5 - Demos


# 6 - Next

Config
- Static values (only changes per environment)
  + In Consul
- Dynamic values
  + In Consul
- Secrets
  + In Vault


https://github.com/boundary/cascade         (Transitional orchestration shell)
https://github.com/boundary/chef-cascade    (Chef code as packages)












