1-Minio_S3Like_ObjectStorage_inGo
---------------------------------

<!-- MarkdownTOC -->

- [Intro](#intro)
- [Demo / Workshop nodes](#demo--workshop-nodes)
- [Why Golang](#why-golang)
- [Tips / Notes](#tips--notes)

<!-- /MarkdownTOC -->



# Intro

Speaker
  - Worked on GlusterFS
  - Now, new project: Minio


> Fun-facts
> --
> 
> Go is great !
> - Static binary, can be put on server withour depending of some distro packages
> - Small, short, efficient: for CLI and admins tools
> => Allowed to create easily CoreUtils like commands to for client side usage of Minio



# Demo / Workshop nodes

* Start the Minio server locally
  - `./minio server ~/work`
  => Start a minio server process that "publish" the 'work' directory as an object storage bucket
  => Start a WebUI: http://127.0.0.1:9001
  => Everything from a static binary


* Ops and usage

```
$ mkdir
$ mc cp -r DIR1 DR2             // Give a progress bar ncurse like
$ mc session resume QWdqwden    // Resume when Network issue
```


# Why Golang

Choices ?

1. C++ for Core and Google v8 for WebUI
  - Was difficult to matained
  - JS / C++ really different

2. Go
  - Efficient
  - Popular, Nice community
  - Suites our use case (+/- portable)

3. Rust
  - Good language
  - But can do samethings in Go

4. Haskell
  - Small comminuty
  - Good if we made a ONLY hosted product

5. C and Python
6. C and Gnu Guile

7. Java
  - Good language, and runtime, and portability
  - Some ObjectStorage are in Java (HDFS, ...)
  - BUT jvm dependency ...
  - BUT JVM Overhead for the Client CLI utilities


Summary: 
Go
- C like feeling
- Python ease
- Java "portability"

> 
> Also really need the ease of usage and the community (Aws s3 "concurent")
> 



# Tips / Notes

* Warning: $GOPATH / $GOROOT
* Expected: $GO15VENDOREXPERIMENT
* Makefile is your friend :)
* Error Handling
  - Debug   (go package)
  - Logrus  (go package)









