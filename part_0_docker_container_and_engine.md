## Docker Container
Docker container is the heart of docker. It is a loosely isolated environment running
within a host machine kernel allows to run app-specfic code along with dependencies.
**Kernel** is a software at the core of OS with complete control of system resources.
It handles resources(hardware or software) for the entire OS.
Docker must run on top of a kernel, which is also called the **host machine**.

## Docker Engine
Docker Engine is the system that handles docker services. It consists of docker
server, an API and a command line interface(that allows interaction with API).
The server is also called **docker daemon**. Daemon meaning background processes
in an OS. Requests are sent through CLI, which then sends them to the daemon.
The docker daemon is like a construction team on the host machine that has blueprint
for various containers. Those blueprints are actually APIs.
CLI -->(requests to create container) --> Docker Daemon(sitting on host kernel) -->(Containers created)

## Features of Docker Containers
* The process of one container cannot affect the processes of another.
* Resource Limitation can be set, esp. for CPU and memory.
* Application-specific code exists within that container including dependencies.
Dependency presence not required on host machine.

## Containers Importance
* Portability for multiple OS environments.
* Less time for settings of environments(dependencies).
* Multiple environments with its own purposes.

## Containers v/s Virtual Machines
* Containers are comparatively light weight.
* VMs abstract an entire computer systems.
While file systems can be shared among containers.  
***NOTE***: If no sharing and a complete isolation is required, VM is a better image

## Docker Images
Containers are created by objects in docker called **Image**.
Images are read-only templates with instructions for creating a Docker Container.
The instructions define container code libraries, softwares, environment variables,
config files and more. The instructions are collected in executable package which is
the image itself. Container is the result of instruction execution written in images.
E.g. image that tells docker to run Ubuntu, or Nginx.  
Docker Image is accessible set of instructions for container creation.
Image to Container relationship is similar to Class to Object relationship.
One image can create many containers.

**DockerHub** is a collection of images from docker users and is hosted in online repositories.

## DockerFile
Outline instructions for how an image will create a container.

## Example of running a ubuntu containers
* Go to hub.docker.com
* Search for the image you want to install and execute the instructions given
***OR***
* Open terminal and check whether Docker is working by running ```docker```.
* Run ```docker search <image name>```. Docker searches all images in Docker Hub
and shows the result.
* ```docker create --name=foo -it <image name> <args>``` to create the container.
E.g. ```docker create --name=foo -it ubuntu bash```.  
This creates a container with the image *ubuntu*, but does not run it.
Just a file system is created. Hence, when ```docker container ls``` does not
list the container just created.
To see all container, running or not, run ```docker container ls -a```.  
To start a container, ```docker start <container name>```. Due to the flag *-it*
added while creation of container, it can be opened in this console.
Run ```docker attach foo```, to launch the container named foo in the console.
The tag in the console immediately changes from *username* to *root@<containerid>*.

Suppose ubuntu container is launched. The following commands will work in this console:
* ls
* apt-get update
etc. In short, all linux commands will work here. To return back to main machine, use
ctrl+pq. Using ctrl+d will stop the container.
In the main console session, ```docker logs foo``` will show all the commands and results
that were executed in the foo container.

### Remove a docker container from host machine
The command ```docker rm foo``` will remove the *foo* named container from host machine
and free memory. This command will through an error if the container is running and
an attempt to remove it is made. To stop a container, ```docker stop foo``` is executed.
