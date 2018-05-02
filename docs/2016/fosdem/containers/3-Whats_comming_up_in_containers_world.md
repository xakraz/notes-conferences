3-Whats_comming_up_in_containers_world
--------------------------------------

<!-- MarkdownTOC -->

- [1- Currently working on](#1--currently-working-on)
- [2 - Mount from User Namespaces](#2---mount-from-user-namespaces)

<!-- /MarkdownTOC -->


Integrating new feature in the Linux Kernel


# 1- Currently working on

* cgroup namespaces: Target Kernel4.4
  - Especially needed to run Docker NESTED into LXC by example
  - Virtualize the view of Cgroups from a running container
  - Mount cgroupfs

* Namespaced files capabilities
  - Allow containers to lay down file caps
  - Without risking host being tricked

* Tag `security.nscapability` with a RootID
  - KernerUID / RootID
  - Allow more than 1 entries



# 2 - Mount from User Namespaces

* VFS changes
  - Superblock user namespace: `s_user_ns`
  - SUID translation support
  - File capabilities
  
* FS targeted: FUSE
  - Already support unpriviliged mounts
  - U/G id translation
  - PID translation

> FUSE Security concern
> --
> 
> * For Security reason: Unprivilieged mount only accessible to the unprivilged user who mounted the FS


* FS targeted: Ext4
  - U/G id translation
  - Limit privileged mount options
  - Journal device access
  - Backing store attacks


* FS targeted: LoopFS
  - Allow user namespaces to allocate loop devices





