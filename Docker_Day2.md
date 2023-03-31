# Docker_Labs
## Docker_Lab2

#### Flow 
![12](https://user-images.githubusercontent.com/128603198/229160482-c7b6e00a-43f6-4c06-9bf9-154e3c36229d.png)

## In Dockerfile

``` bash 

FROM mysql:latest

ENV MYSQL_ROOT_PASSWORD=P4sSw0rd0!

VOLUME /var/lib/mysql

EXPOSE 3306

```

## To Build Docker Image
``` bash
docker build -t mysql-with-volume .

```



## P3: What is the rest of Docker Networks ? “Name and Definition”


``` bash
1- Bridge Network:
A bridge network is the default network driver used by Docker. It allows containers to communicate with each other even if they are on different hosts. Containers on a bridge network are isolated from containers on other bridge networks.

2- Host Network:
The host network mode allows a container to use the network stack of the host machine, rather than having its own network stack. This mode can be useful for containers that require access to a host network interface, such as for performance or security reasons.

3- Overlay Network:
An overlay network is a multi-host network that allows communication between containers running on different Docker hosts. This network type is commonly used in Docker swarm mode, which is a Docker-native clustering and orchestration system.

4-Macvlan Network:
A macvlan network allows a container to have its own unique MAC address, which makes it appear as a physical device on the network. This network type is useful for applications that require direct access to the physical network.

5- None Network:
The none network is a network driver that disables networking for a container. Containers running with the none network driver can only communicate with the host machine and other containers using the --link option.

6- Third-party Network Drivers:
Docker also supports third-party network drivers, which can be used to create custom network configurations and enable communication between containers using non-standard protocols.

```

## P4: What is the different between docker images tags ?

``` bash

1- Latest:
The latest tag is a special tag that is used by default when no specific tag is specified. This tag points to the most recent version of the image. However, the latest tag does not necessarily point to the latest version of the image.

2- Specific Version:
A specific version tag is a tag that points to a specific version of the image. For example, mysql:5.7 points to version 5.7 of the MySQL image.

3- Unique Tag:
A unique tag is a custom tag that can be used to identify a specific version of an image. Unique tags are typically used in CI/CD pipelines to track and manage images as they move through the pipeline.

4- Alias Tag:
An alias tag is a tag that is used to create an alias for another tag. For example, nginx:stable might point to the most stable version of the Nginx image.
```
