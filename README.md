# Docker For Beginners
***Source***: Udemy
## Terminologies:
**Docker**: Docker is a platform that lets where applications can be packaged,
developed and run in containers.  
**Container**: Container is a virtual environment on top of the OS kernel to
capture all its software - libraries, dependencies, etc.

There can be many containers sitting on the same base level kernel. Yet each container
has its own space on top of OS. The container run its own code in private environment.
Each container has its isolation and cannot be invaded by another container.

## Why Docker exists
A lightweight approach than virtual machine to isolated coding and project environments.
Consider 5 isolated environments are required to run 5 different applications in
a project, with each needing a separate environment. Creating 5 VMs will take a lot
of space as each VM has its own set of OS and applications. Docker provides solution here.

The common libraries among containers are shared, hence optimising space utilisation.
Docker is portable in the sense that a container running in one machine
(independent of OS) and can run in another machine with docker. It supports major
architecture and operating systems. It helps achieve CI/CD(continuous integration
continuous development) for develop operations.

## Installation
Docker can be installed free of cost from https://docs.docker.com/ and follow the Installation
guide given there. Once done, to check if docker is up and running, run *docker* in cmd/terminal.

## Contents
Part 0 : [Docker Container and Engine](https://github.com/code-lucidal58/learning_docker/blob/master/part_0_docker_container_and_engine.md)
