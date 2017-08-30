4-Docker_for_developer
----------------------

<!-- MarkdownTOC -->

- [Intro](#intro)
- [Basic usages](#basic-usages)
- [Unit Tests](#unit-tests)
- [Other use cases](#other-use-cases)
- [Challenges](#challenges)

<!-- /MarkdownTOC -->


# Intro

* Docker is popular
* Focus on deployment (with all k8s, swarm, ecs and stuff)

* You can also use docker on a daily bases 
	- 1 developer
	- 1 laptop
	- Without saying that you use Docker :)
	=> Based on Jessie Frazel stuff



# Basic usages

1. `--rm`
2. `--volume`

```shell
docker run --rm \
					 --volume $WORKSPACE:/somewhere/in/the/container/according/to/the/software/best/practices
					maven:4.0.4
					package
```


3. `links`
4. '-it'

=> Ephemeral, reproducable, fast shell environment



# Unit Tests

Proble usecase

* Test Matrix
  - Make a docker images for every system you need
  - Same RUN command
  - Reproducable
  - Explicit and versioned dependencies (when relying on system packages)

* Complex "Topology" testing (Infrastucture)
  - Run the really important process component into a container
  - Use compose + Links

* Simulating load

* Easy DB state reset
  - Nothing to "reset"



# Other use cases

* Integration Tests
  - Mocking services  
* Demos
* Data migration test
  - "Data" containers

* Shared and reproducable environment in Team
  - With private registry


# Challenges

* Shared stuff
  - Secrets
  - config
  - Everything that is not "Runtime" related




