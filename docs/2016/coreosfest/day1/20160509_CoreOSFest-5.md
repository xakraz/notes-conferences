20160509_CoreOSFest-5
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
- [2 - Containers](#2---containers)
- [3 - DGR](#3---dgr)
  - [Concepts](#concepts)
  - [Project](#project)
  - [CLI](#cli)
- [4 - Next](#4---next)

<!-- /MarkdownTOC -->


DGR: An Appc image builder tool



# 1 - Intro

* Blablacar
* Exponential grow (+20M user in 2 years)
* Own DC + Bare Metal



# 2 - Containers

* CoreOS had pretty attractive **concepts**
* At the time `Rkt` was new kid of the Block
-> Bleeding edges


Tries to build images:
* Chef (We used chef at the time)
* Packer
* Acbuild
-> Build our own wrapper around `acbuil` to map Blabla workflow



# 3 - DGR

https://github.com/blablacar/dgr

## Concepts

* YAML format
* Dependencies concepts (FRON Images)
* Config Templating
* Test included


## Project

```
PROJECT
|
├── aci-manifest.yml
|
├── attribures/
├── templates/          // Go templating
|
├── tests/
└── runlevels/
    └── build/
        └── install.sh
```


```
install.sh
-----------

#!bin/xxxx/busyx-box ...

SHELL SCRIPTING
```


## CLI

```
dgr init      // Bootstrap Project structure
dgr try       // Template rendering
dbr build
drg test
dgr install   // In local RKT image store
dgr push      // Only support for NEXUS TARG.GZ repo
```



# 4 - Next

* Sign ACI
* Push to other repos
* Orchestrate
