2-Hardening_cfg_mgnt
--------------------

<!-- MarkdownTOC -->

- [Intro](#intro)
- [Where to start](#where-to-start)
- [1 - Data laying around](#1---data-laying-around)
- [2 - Data encryption](#2---data-encryption)
- [3 - Other stuff to keep in mind](#3---other-stuff-to-keep-in-mind)
- [4 - Resources for Auditing](#4---resources-for-auditing)
- [5 - SSH](#5---ssh)

<!-- /MarkdownTOC -->


# Intro

* Security
  - is hard
  - puts constraints
  - nobody cares because, functionaly, it works

* Cfg mgnt is now the SPOF / Target (from security pov)


# Where to start

* Google Search: "Hardening cfg mgnt"
  - OWASP
  - 1/2 Google groups asking question

=> NO real insight


* Security principles
  - ...
  - ...



# 1 - Data laying around

Example with Puppet
  - Use Hiera
  - Remove any credentials or data from Module
  - Publish in 1 "init" commit by removing the history



# 2 - Data encryption

* External source
  - Hiera-eyaml
  - Chef-vault
  
* External secrets service
  - Cloudflares/Redoctober
  - Hashicorp/valult

* Git in repo content
  - git-crypt

=> Stay in control



# 3 - Other stuff to keep in mind

* Do lint, reviews, continuously
  - Rbac
  - chef-inspec

* Also keep in mind the risk if people get access to you CFG mnt infra
  - Agents reporting logs
  - Disable diff of changes
  - ...

* Monitor the activity of your apps
  - 40X / 50X
  - Logs
  - Behavior

* Security baseline
  - Best practices
  - Defined shared rules



# 4 - Resources for Auditing

* hardening.io
* CIS (Central Internet Security)
* Chef has integrated its own "Audit" mod
* SIMP Github organization



# 5 - SSH

* Even if you use Agent based CFG mgnt
  - SSH is / will still be there
  => Check your config
  => Rotate your keys

* Have you thought to:
  - Disable SSH completly



