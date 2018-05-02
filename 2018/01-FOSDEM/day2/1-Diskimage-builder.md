# 1 - Diskimage-builder


<!-- MarkdownTOC -->

- [1 - Before](#1---before)
- [2 - Disk image builder](#2---disk-image-builder)
  - [Example](#example)
  - [Support Matrix](#support-matrix)
- [3 - Details](#3---details)
  - [Elements](#elements)
  - [Block Device Layer](#block-device-layer)
  - [Block Device Later MBR module](#block-device-later-mbr-module)
  - [Tips](#tips)

<!-- /MarkdownTOC -->




## 1 - Before

Building OS the "trad" way
- Iso (+ kind of automation KS / Preseed)
- OS Treee (DebootStrap)


Issue:
- For each OS, you have a different tool
- Expodential combinaison


Goal:
- 1 to rule them all




## 2 - Disk image builder

### Example

```
disk-image-builder debian-minimal vm
disk-image-builder fedora-minimal vm
disk-image-builder centos-minimal vm

disk-image-builder -o docker debian-minimal
```


### Support Matrix

Combinaison:
* OS
* Arch
* Env (VMWare, OpenStack, KVM, AWS, DOcker, Bare-metal)

Qemu is used for Arch and Image convertion




## 3 - Details

### Elements

>
> Like puppet-modules, ...
>

An element is:
- Collection of config files
- Collection of dirs
- Collection of scripts

```
README.rst
element-deps
package-installs.yaml   (By Arch)

environment.d/          (Export ENV variables)

root.d/                 (Scripts)
```



### Block Device Layer

Hierarchie:
0 - Disk space, loop device, ...
1 - Partitioning / LVM
2 - FS generation
3 - Mount
4 - FSTab handling

-> Yaml file config with actions for each layer



### Block Device Later MBR module

-> OK


### Tips

Build lean OS image and pass it to your config Management system


