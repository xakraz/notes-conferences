6-Twitter_infrastructure_with_containers
----------------------------------------

<!-- MarkdownTOC -->

- [Twitter Scale](#twitter-scale)
- [THe problem](#the-problem)
- [Twitter Workflow](#twitter-workflow)
- [Scheduler](#scheduler)

<!-- /MarkdownTOC -->



# Twitter Scale

10^5 : Containers
10^4 : Hosts
10^3 : Jobs / servcices
10^2 : Teams
10^1 : SREs/Team



# THe problem

Twitter focus;
* Scale -> efficiency

> Tips:
> --
> 
> * Don't care of efficency if you are not at that scale
> * Care about easiness and usage
> 



# Twitter Workflow

* Mesos
* Aurora (service / jobs)

1. User define a need in Json
2. Submit to the scheduler
3. Enjoy



# Scheduler

* Linux default: CFS



