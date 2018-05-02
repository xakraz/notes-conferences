20160510_CoreOSFest-7
---------------------

<!-- MarkdownTOC -->

- [1 - Intro](#1---intro)
- [2 - Sec features](#2---sec-features)

<!-- /MarkdownTOC -->



Keynote: Security in systemd



# 1 - Intro

Sandbox everything
* Not only containers, system services too


What diff 'System service' vs 'Container' ?


Systemd-nspawn
* User namespace that work



# 2 - Sec features

`PrivateTmp=yes|no`
* Private instance of `/tmp` and `/var/tmp`
* Lifecycle is bound to service runtimes

`JoinsNamespaceOf=`
* Allow IPC between services that use some UNIX sockets in `/tmp`

`CapabilityBoundingSet=`
* FlagBits to give very specific permissions (Example, NTP priviliges to set Host clock)

`AmbiantCapabilities=`
* Heritage of capabilities

`PrivateDevices=yes|no`
* Shared devices are `/dev/null` and so on that are part of Unix API

`ProtectHome=yes|no|read-only`
* If service is exploited, won't be able to access admin home and access keys or some private stuff

`MountFlags=false`
* Capacity to edit Mount table file

```
ReadWriteDirectories=
ReadOnlyDirectories=
InaccessilblesDirectories=
```

...








