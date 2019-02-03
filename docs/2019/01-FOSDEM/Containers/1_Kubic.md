# 1_Kubic

<!-- MarkdownTOC -->

- [0 - Overview](#0---overview)
- [1 - Solid tool chain and echosystem](#1---solid-tool-chain-and-echosystem)
- [2 - NOT docker](#2---not-docker)
- [3 - Misc](#3---misc)

<!-- /MarkdownTOC -->



## 0 - Overview

Doc:
- https://en.opensuse.org/Portal:Kubic

OpenSuse Container centric Project

`MicroOS`:
* Current version based on OpenSuse Tumbleweed
* RO RootFS
* Atomic Updates
* Containers toolchain
  - `k8s` 1.13
  - `kubeadm` 1.13
  - `Podman`, `Skopeo`, `Buildah`, ...
  - `CRI-O` (NOT Docker !)

-> Not part YET of CNCF but k8s certified !



## 1 - Solid tool chain and echosystem

- [OpenBuild system](https://build.opensuse.org)
- [OpenQA](https://openqa.opensuse.org/)
- [registry.opensuse.rog](https://registry.opensuse.org/cgi-bin/cooverview)



## 2 - NOT docker

`CRI-O`: Container Runtime
- Simpler, lightweigh
- Integrated to k8s release pace
- Compatible

`Podman`
- docker like CLI approch
- Lets you create, use PODS on local machine (outside of k8s)

`Buildah`
- Build OCI images
- Compatible Docker
- Support `Dockerfile`



## 3 - Misc

Links:
- https://en.opensuse.org/Kubic:kubeadm
- https://github.com/kubic-project/kubic-init
