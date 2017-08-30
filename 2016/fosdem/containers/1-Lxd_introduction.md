1-Lxd_introduction
------------------

<!-- MarkdownTOC -->

- [1 - LXD](#1---lxd)

<!-- /MarkdownTOC -->


# 1 - LXD

* What's LXD
  - simple CLI
  - Fast: LXC containers
  - Secure: Use Kernel security feature and namespaces (next: capabilities support)
  - Scalable: Daemon + REST API running of multiple Hosts

* What LXD is NOT
  - NOT virtualization (Even if "full" OS running thanks to LXC)
  - NOT a fork of LXC (Part of the team of LXC)
  - NOT an application manager (not like K8s / Mesos marathon, ...)


> Demo
> --
> 
> https://linuxcontainers.org/lxd/try-it/
> 
> * Admin:
>   - Can do HOT resources properties changes
>   - Intergation with Host FS for snapshoting (ZFS, BTRFS, soon LVM2)
> 
> * Interaction:
>   - Nice CLI to interract with a running container
>   - `lxc push file <container>`
>   - `lxc pull <container>:file <host>:<PATH>`
>   - `lxc edit`
>
> * Images:
>   - Based on Git workflow with REPOS
>   - `lxc remote`
>   - `lxc push`
>   - `lxc pull`
> 


* Next
  - Support for Docker container format
  - Improve migration (running state)
  - Integration into openstack
  - Integration into Juju

* Contribute
  - Go
  - API clients in Go and Python (Currently)
  - Apache2 Licence




