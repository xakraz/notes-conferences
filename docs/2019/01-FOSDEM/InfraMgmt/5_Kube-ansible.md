# Automate Kubernetes Workloads with Ansible

<!-- MarkdownTOC -->

- [0 - Overview](#0---overview)
- [1 - Ansible Playbook Bundle](#1---ansible-playbook-bundle)
- [4 - Service Catalog](#4---service-catalog)
- [6 - Operators](#6---operators)
- [CCL](#ccl)

<!-- /MarkdownTOC -->



## 0 - Overview

https://fosdem.org/2019/schedule/event/automate_kubernetes_ansible/


Ansible Operator in Kube
- https://opensource.com/article/18/10/ansible-operators-kubernetes
- https://opensource.com/article/18/2/automated-provisioning-kubernetes

-> Watch events from Kube and runs some Ansible task to make 'reconciliation'



## 1 - Ansible Playbook Bundle

* Bundles everything you need at provision time
* CRD that runs on your cluster
* Runs to completion



## 4 - Service Catalog

Concept of "ServiceCatalog" in Kube ecosystem
* Provides composable services to applications
* Actions
  - Provision / Deprovision
  - Bind / Unbind

-> Bring selfservice to cluster users


Notion of brokers


Automation with Ansible
- Service bundles
-> Catalog entry
-> Run completion
-> Run in a secire sandbox
-> Remove the need to ....


Tips:
* `svcat`
* KubeApps


Status
* Great path for Automated and self-service provisioning that works today
* Off-cluster integration is the best use case
* /!\ Lack a "day 2" management




## 6 - Operators

* A kube controller
* Deploys and manage an application
* Human operation knowledge in code



## CCL

* Ansible playbook to deploy k8s clusters
* Ansible modules to deploy components into k8s
* Ansible operator to maintain you app in k8s

+ ServiceCatalog
