1-Containers_and_virtualization
-------------------------------

<!-- MarkdownTOC -->

- [Intro](#intro)
- [Virtu & Atomic](#virtu--atomic)
- [Demo](#demo)

<!-- /MarkdownTOC -->


https://fosdem.org/2016/schedule/event/virt_iaas_containers_and_virtualization/

Spoiler: Containers and VMs can work together

* Manage **virtualization / IaaS technologies** 
* With containers to make them easier to deploy and manage. 
=> Efforts to containerize things like oVirt and OpenStack, as well as the best way to run KVM virtual machines in privileged containers.



# Intro

* Cloud / Virtualization was the new hotness
* Then orchestration of VMs
* Now Containers
* Then orchestrate Containers



# Virtu & Atomic

* Atomic Project
  - Minimal os
  - Everything as a container
  - No packages
  => CoreOS like
  => From RedHat


* Koala Project
  - Openstack services as container
  - Deployed with Ansible


# Demo

* Workstation: Fedora23
  - Vagant **VM** Host: Atomic
    + **Container**: Fedora23 with Libvirt
      * Vagrant **VM** Host: Atomic










