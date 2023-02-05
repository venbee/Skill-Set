## Docker Notes

- Docker is used to Containerize Applications and also to Run each service with its own dependencies in separate containers.
- Docker image is an template which can be created manually or can be pulled form docker hub.
- Docker containers are instances of docker images.
- In a machine, we can create a docker host and inside that we can create docker images and containers
- To remove an docker image from the docker host, first we need to remove the containers running on that image and for removing containers first that containers need to be stopped.
- rm is used to remove containers and rmi is used to remove images in docker host
- if we run an docker image with sleep 1500 or something like that, then we can't do any operations in that terminal. In this case, we can open a new terminal and then stop the running instance.
- For porting, a container will be having an ip address and same with the docker host. 
- A docker host can be browsable in local machine, but it is not same with the container(it won't reach outside the docker host)
- To implement this, we need to do porting of the docker container ip address with docker host ip address (80:5000), here 80 is host port and 5000 is container port.
- when we running an container, and after if we delete it all the data related to it will also be deleted. 
- To Save the data, we can do volume mapping so that the docker container data will be stored inside docker host storage
- 
