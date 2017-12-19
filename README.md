# docker-jenkinsslave-ubuntu

Jenkins Slave docker image, based off [OpenJDK](http://openjdk.java.net/) 8 on [Ubuntu](https://www.ubuntu.com/), with [Gradle](https://gradle.org/) and [Maven](https://maven.apache.org/) installed

This is available on Docker hub as [garethjevans/jenkinsslave-ubuntu](https://hub.docker.com/r/garethjevans/jenkinsslave-ubuntu/)

## Usage

To create a basic Jenkins (Ubuntu) Slave instance use:

```
docker run \
    --detach \
    --env JENKINS_MASTER=<JENKINS_MASTER_ADDRESS> \
    --env JENKINS_USERNAME=<JENKINS_USERNAME> \
    --env JENKINS_PASSWORD=<JENKINS_PASSWORD> \
    --env JENKINS_EXECUTORS=1 \
    --env JENKINS_LABELS=build \
    --env JENKINS_NAME=ubuntu-build-slave \
    --env LANG=C.UTF-8 \
    --name jenkins_ubuntu_build \
    --volume /etc/localtime:/etc/localtime:ro \
    garethjevans/jenkinsslave-ubuntu:latest
```

Obviously, you'll need an instance of Jenkins Master as well, try [garethjevans/jenkins](https://hub.docker.com/r/garethjevans/jenkins/).
