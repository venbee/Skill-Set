### Docker for the Absolute Beginner - Hands On - DevOps -- Udemy

To find the version of docker installed

```bash
  docker version 
```

To run a normal docker image

```bash
  docker run nginx
```

To list the containers in docker host

```bash
  docker ps
```

To list the containers in docker host both running and not running

```bash
  docker ps -a
```

To stop a docker container

```bash
  docker stop "container-id"
```

To remove a container

```bash
  docker rm "container-id" or "container-name"
```

To list the docker images available on docker host

```bash
  docker images 
```


To remove a docker image from docker host

```bash
  docker rmi "image-name" or "image-id"
```


To pull a docker image but not run it in host

```bash
  docker pull nginx
```


To run a image for particular time(ex:10 seconds)

```bash
  docker run ubuntu sleep 10
```


To execute a particular command on an conatainer instance

```bash
  docker exec "container-name" cat /etc/hosts
```


To run an instance in detach mode

```bash
  docker run sample-web-app
  docker run -d sample-web-app 
```


To attach the above instance which is attached

```bash
  docker attach "container-id"
```


To run an image

```bash
  docker run redis
```


To run an image with tag (tags details can be found in docker hub)

```bash
  docker run redis:4.0
```


To run an application in interactive mode

```bash
  docker run -i sample-web-app
```


To run an application in interactive terminal mode 

```bash
  docker run -it sample-web-app
```


To run an docker container with name specified

```bash
  docker run -d --name webapp nginx:1.14-alpine
```


To do port mapping for a container inside docker host

```bash
  docker run -p 80:5000 sample-web-app
```


To run a docker container with volume mapping

```bash
  docker run -v /opt/datadir:/var/lib/mysql mysql
```


To inspect a container (for finding versions, ip_address)

```bash
  docker inspect "container-name"
```


To find the logs of a container

```bash
  docker logs "container-name"
```


To run an ubuntu image with tag and also see the release version

```bash
  docker run ubuntu:17.10 cat /etc/*release*
```


To run an ununtu image for 1500 seconds

```bash
  docker run ubuntu sleep 1500
```


To run an jenkins image with porting and also do the volume mapping

```bash
  docker run -p 8080:8080 -v /root/my-jenkins:/var/jenkins-home -u root jenkins
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```


To 

```bash
  docker 
```



## The Docker Handbook – Learn Docker for Beginners --> freeCodeCamp 


