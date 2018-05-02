# 2 - Mozilla Molotov


<!-- MarkdownTOC -->

- [1 - Webservices / WebApps](#1---webservices--webapps)
- [2 - App under Stress](#2---app-under-stress)
- [3 - Test ?](#3---test-)
- [4 - Distributed systems ?](#4---distributed-systems-)
- [5 - Molotov](#5---molotov)
  - [Desc](#desc)
  - [Features](#features)

<!-- /MarkdownTOC -->



## 1 - Webservices / WebApps

Webapp
* Client-side
* User Auth
* Lots of caching

Webservices
* As dumb as possinble
* App 2 App transaction



## 2 - App under Stress

Goals
* What do we exhaust first under high load ?
* When (Conditions)
* Behavior
* Recover ?



## 3 - Test ?

Metrics
* Myth of client-side feedback

Existing Tools
* AB
* Boom (AB in Go)
* JMeter
* Grinder
* Bees (Aws based)
* Locust (Pythonm Zmq, Gevent)



## 4 - Distributed systems ?

* Hard

-> Molotov



## 5 - Molotov

### Desc

* Pyhton3
* KISS
* Framework
* Based on AIO

-> 30k RQPS on a laptop

http://molotov.readthedocs.io/en/stable/


### Features

* Multi-scenario support
* Remove scenario support (Github + Json)
* CSV export
