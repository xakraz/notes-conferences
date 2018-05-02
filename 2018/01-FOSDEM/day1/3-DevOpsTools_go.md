# 3 - Distributing DevOps Tools for fun and Profit


<!-- MarkdownTOC -->

- [1 - Past](#1---past)
- [2 - Docker](#2---docker)
- [3 - Better distribution](#3---better-distribution)
- [4 - OpenSource: Cali](#4---opensource-cali)

<!-- /MarkdownTOC -->




## 1 - Past

Vagrant with
* Chefdk
* Docker
* Git
* Terraform
* Vault
* AWS Cli
* ...


Issues:
- Bigs
- Slow
- Take time to build
- Hard to maintain



## 2 - Docker

Docker:
* For Mac
* For Windows
* Linux native

The past -> bash aliases



## 3 - Better distribution

`PSCLI`
* Docker + Cobra/Viper

Features:
* Self updating
* Bind $PWD
* Run with Local + Remote docker
* Anonymous usage statistics <----- WOW !
* Run arbitrary code before launching container
  - Authen against vault
  - Generate STS creds
  - ...



## 4 - OpenSource: Cali

https://github.com/skybet/cali



