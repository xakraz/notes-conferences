20160614_3_BringMamothToCI
--------------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
- [2 - Service Discovery](#2---service-discovery)
- [3 - Secrets management](#3---secrets-management)

<!-- /MarkdownTOC -->




# 1 - Intro

...



# 2 - Service Discovery

Consul


Infra:
* Docker-swarm
* Consul-registrator
* Consul


3 Environments:
* 1 Docker-swarm cluster / env
* Other **Consul KV store** for "Automation"
  - 1 cluster between each environment
  - KV values are:
     + CI variables: Version of containers
     + Apps variables: Configuration

  => Dynamic



# 3 - Secrets management

Vault


Main use case: 
1. Dynamic / On demand credentials generation
  => Each instance has dedicated creds
  => Great Auditlog
  => No hard-coded values

2. Same for Users, during troubleshooting needs
3. PKI Management

