Here we will read about docker images in depth and how to create a custom docker
image.

## DockerFile
As mentioned earlier, docker file is a read-only  set of instructions which assemble
to create a docker image. It is a text file with commands which correspond to docker
container commands. For example, ```docker create <image>``` should refer to
**FROM** command in docker file. Docker file commands are distinguishable from its parameters
as they are all in CAPITAL CASE. Other commands are RUN, CMD, COPY, etc.
These are the backbone of imaging system in docker.
One such example of Docker file for *redis* image is
[here](https://github.com/docker-library/redis/blob/dcc0a2a343ce499b78ca617987e8621e7d31515b/5.0/alpine/Dockerfile).
Other docker images can found found in hub.docker.com
