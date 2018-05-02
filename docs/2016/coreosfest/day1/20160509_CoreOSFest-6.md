20160509_CoreOSFest-6
---------------------

<!-- MarkdownTOC -->

- [1 - Pb](#1---pb)
- [2 - Squashed images](#2---squashed-images)
- [4 - BitTorrent distributions](#4---bittorrent-distributions)
  - [Why bittorrent?](#why-bittorrent)
  - [Quay.io implementation](#quayio-implementation)
  - [Security?](#security)
- [5 - Perf benefits ?](#5---perf-benefits-)
- [6 - Side projects](#6---side-projects)
- [7 - FAQ](#7---faq)

<!-- /MarkdownTOC -->


Image distributions



# 1 - Pb

How images are pulled ?
* Pull from a platform called "Registry"
* API over HTTP
* Images have format (Docker images v1/v2 / ACI)

Docker images
* Layers
* .tar.gz layers

How many request for images ?
* List of Tags
* Metadata
* 1x for each parent (meh)
* BLOB of each layer
=> 10 rqst for a 3 layers image



# 2 - Squashed images

Docker layers:
* Each layer is .tar.gz
* `docker load` take .tar.gz
-> Real time squashing

Squashing process
* Parse each layers to not keep the deleted / overwritten files
* Tar on the fly
* Respond to client + Store squashed image (for later requests)

Squashed downsides
* No more benefits of shared layers
* Realtime squashing is slow
* LOAD cmd requieres more memory



# 4 - BitTorrent distributions

## Why bittorrent?

Pulling does not scale
* Each Container node makes HTTP requests to the registry
* But they are all requesting the same data
=> Share the data among the cluster

Torrent today
* Used for many content distribution
* Scale at "core" concept


## Quay.io implementation

```
quayctl docker  torrent pull  xxx
quayctl rkt     torrent fetch xxx

quayctl rkt     torrent seed xxx --duration=YY
quayctl rkt     torrent seed xxx --squashed
```


## Security?

* Private repo supports
* Credentials support
* Torrent swarm node trust support



# 5 - Perf benefits ?

Test: 30% Traffic reduction



# 6 - Side projects

Blog post: https://blog.quay.io/torrent/
ACI registry: https://github.com/containerops/dockyard



# 7 - FAQ

* k8s integration?
  - WIP

* OWn on premise BT tracker?
  - Quay.io provide tracker service + Authentication
  - Provide some OSS pieces if you want to run your own

* IPFS for distribution?
  - We have quikcly looked at it.
  - Still young
  - Some privacy issue at the time
  - But keep an eye on it