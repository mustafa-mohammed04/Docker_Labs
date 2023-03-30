## Docker Labs_Problem-1

![2](https://user-images.githubusercontent.com/128603198/228682380-e8dbe657-a99d-430d-8347-79aee277fc82.png)

``` bash
    apt install docker.io
    docker version
    docker run hello-world
    docker ps -a
    docker start 96e8a5ca013a
    docker ps
    docker rm 96e8a5ca013a
    docker rmi hello-world
    docker images
```

##  Docker Labs_Problem 2
![3](https://user-images.githubusercontent.com/128603198/228682423-c0956638-c6b7-49e1-9a96-b60a62c72ef8.png)


``` bash
   docker run -it centos /bin/bash
   bash
   touch hello-docker
   exit
   docker stop 707f7448bb0d
   docker rm 707f7448bb0d

```

## Docker Labs_Problem 3
![4](https://user-images.githubusercontent.com/128603198/228682492-e2d46d79-cec5-47f1-843f-d53a8a3459a8.png)


``` bash
  mkdir docker_dir1
  docker run -d -p 9898:80 --name apache -v "$(pwd)/html:/usr/local/apache2/htdocs/" httpd:latest
  docker ps -a
  docker rm a9c2083eb282
  docker run -d -p 9898:80 --name apache2 -v "$(pwd)/html:/usr/local/apache2/htdocs/" httpd:latest
  ufw allow 9898
  curl localohost:9898
```


## Docker  Labs_Problem 4
![5](https://user-images.githubusercontent.com/128603198/228682525-653f43ad-13f3-481b-8b16-a5121960146e.png)

``` bash
  docker run -d -p 80:80 --name apache httpd:latest
  docker cp html/index.html apache:/usr/local/apache2/htdocs/
  docker cp html/index.html apache:/usr/local/apache2/htdocs/
  docker commit apache my_apache
  vi index.html  >> Hello Docker
  docker rm apache
  ufw allow 80
  curl localohost:80
```

## Docker Labs_Problem 5
![6](https://user-images.githubusercontent.com/128603198/228682536-f6886923-06e5-46ca-aad6-d41f0505fc44.png)

``` bash
   docker volume create mysql_data
   docker volume ls
   docker run -d -e MYSQL_ROOT_PASSWORD=P4sSw0rd0!.M --name app-database -v mysql_data:/var/lib/mysql mysql:latest
   
```
