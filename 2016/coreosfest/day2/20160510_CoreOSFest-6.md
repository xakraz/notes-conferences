20160510_CoreOSFest-6
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
  - [k8s](#k8s)
  - [API server](#api-server)
- [2 - Auth Flow](#2---auth-flow)
  - [AuthN \(Authentication\)](#authn-authentication)
    - [Existing plugins](#existing-plugins)
    - [Dex](#dex)
  - [AuthZ \(permissions\)](#authz-permissions)
    - [Existing plugins](#existing-plugins-1)
    - [New](#new)

<!-- /MarkdownTOC -->



Kubernes + Dex



# 1 - Intro

## k8s

Worker
* Kubelet (worker)
* Proxy (Iptables manager on Host)
* Container engine (Docker / Rkt)

K8s Control Plane
* **API server**
* Controller
* Scheduler

Admin CLI
* REST API
* `kubectl`

+ Relies on `etcd` for state


## API server

* Main block (Everything talks to the API server)
* Auth PLUGIN mechanism



# 2 - Auth Flow

## AuthN (Authentication)

### Existing plugins

AuthN plugins
* x509
* Passwords / Tokens files
* OpenStack Keystone
* Built-in "Service Accounts"
* Token webhooks (outside source)
* OpenID
* ...

### Dex

Federation:
* K8s -> Dex -> OpenLDAP, Github, Google, ....


## AuthZ (permissions)

### Existing plugins

* ABAC
  - JSON static policy file
* Webhook
  - Outside source

> What happens when remote service dies ?
> --
>
> - User: use remote service
> - Workers nodes: use ABAC style
>

### New

* RBAC
  - YAML format
  - in k8s 1.3

* Kind of permissions
  - AdminControl
  - ResourcesQuotas
  - Limites (Pods point of view)
  - ...














