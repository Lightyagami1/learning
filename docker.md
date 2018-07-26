# Key difference between VM vs container
 + Hypervisor abstract an entire device, container just abstracts the operating system kernel.
 + More containers can be used on same hardware as VMs 

---

# docker info
Prints out various information regarding docker setup of system

# docker run hello-world
to check if docker installation is working properly

# docker ps
 + list out currently running docker images
 + docker ps -a 
   * list out history of status of various docker images

# docker images
 + list out all available docker images
 + IMAGE ID is hash of image

# docker start <container>
# docker stop <container>
# docker rm

 Docker can be persistent or can't be persistent.

 docker run -d --name web -p 80:8080 ImageName
 * -d daemon
 * 80:8080 = host:container port

 docker run -it
 * -it = iterative

 Containers are single process construct
 To exit container
 Ctrl P+Q

 with exit, the process and container will be killed together

 To deal with multiple or all instances of containers
 docker stop $(docker ps -aq)
 -aq = all, quiet mode (returns only id of containers)

---
# SWARM mode
 + true native clustering
 + Type of nodes
   * manager nodes : manages other nodes, in odd number(multiple nodes for H/A of nodes), only 1 master nodes (other nodes are proxy to this master)
   * worker nodes : execute tasks
 + Services
   * Available only in swarm mode
