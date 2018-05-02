20160614_SecureCloud_Hashicorp-tools
------------------------------------

<!-- MarkdownTOC -->

- [1- Intro](#1--intro)
  - [1.1 - Needs](#11---needs)
  - [1.2 - Tools](#12---tools)
- [2 - Challenges](#2---challenges)
  - [Challenge 1 - Images](#challenge-1---images)
  - [Challenge 2 - Infra provisioning](#challenge-2---infra-provisioning)
  - [Challenge 3 - Bootstraping + Configuration of instances](#challenge-3---bootstraping--configuration-of-instances)
  - [Challenge 4 - Secrets management](#challenge-4---secrets-management)
- [3 - Ccl](#3---ccl)

<!-- /MarkdownTOC -->




# 1- Intro

## 1.1 - Needs

Example:
* Team 1 needs a `k8s` based development environment

=> "Environment contract"


ASAP
- Automated
- Separate config / code
- API driven (Cloud and tools)
- Prefer modular, OpenSource tooling


2 Main key features
- Self service functionality
- Automated environment generation



## 1.2 - Tools

Packer
- Images / Build

Terraform
- Modeling infrastructure BLOCKS

CFGMGNT
- Ansible, Chef, Puppet, ...

Vault
- Secrets





# 2 - Challenges

## Challenge 1 - Images


## Challenge 2 - Infra provisioning

Demo / Example: Terraform

- Manifests `terraform.tf`
  + OpenVPN Compute instance
- Variables extracted iin `inputs.tf` file
- Modules structure


```
+ aws/
  + simpled-dns/
    + core.tf
    + inputs.tf
    + outputs.tf
```


Key points
- Multi-cloud support
-> Can go from 1 provider to an other
-> Can conbine x providers




## Challenge 3 - Bootstraping + Configuration of instances

Bootstraping with `Cloud-init`
- Hooks into cloud providers Metadata service
- Allow User-data

=> Terraform can publish User-data into Cloud provider


> Commants
> --
> 
> Goal was to bootstrap the `cfg mgnt` tool ASAP on raw image
> 




## Challenge 4 - Secrets management

Lesson learn: DONT run your own !

Vault
- Unified API for multiple backends
- Policies (permissions)
- Audits

=> The unified and centralized place to manage secrets

Integration effort
- Vary according tools
- BUT since API, at some point we can do / workaround the lack of existing tool


Process:
* Admins can unseal / create mount policyes
* Other users can Changes the values
* User
  1. User submit "Create environment" request
  2. Spin-up environment
    + GET IAAS Creds 
    + (No existing tool, we write some stuff : https://gitjub.com/opencredo/terrahelp)


Benefits:
- Centralised
- Flexible Backends
- API


Fully Automated ? The bootstraping problem:
* Vault custom policy
* IAAS : Cloud-init
  - Not secure (Plain text file on instance FS)
  -> `cubbyhole` temp token for bootstraping





# 3 - Ccl

* Dev can create env in minutes
* Address concerns about moving / locking provider
* Start leverage promise of cloud
* Leson learn for chosing the RIGHT cloud for the Job (Rather than 1 size fits all)


"The only constant in life, is change"


