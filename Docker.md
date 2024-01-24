
`  `**DOCKER DOCUMENT**

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.001.png)**Presented By Simran Popli**

**TABLE OF CONTENT** 

[**Introduction	3**](#_heading=h.z0cn6abiswlz)**

[**Architecture of Docker	4**](#_heading=h.kr2wgfm8q9cp)

[**D](#_heading=h.4ute5o2aogdx)[ocker files](#_heading=h.4ute5o2aogdx)[	6**](#_heading=h.4ute5o2aogdx)

[**Components of Dockerfile	8**](#_heading=h.wog901odjywz)

[**Types of Docker Network	8**](#_heading=h.lv928ctft7yy)

[**Docker Storage	10**](#_heading=h.1sgar3v90oe1)

[**Docker Volume**](#_heading=h.hdpna740xv7a)[	](#_heading=)**12**

[**Port Forwarding In Docker	13**](#_heading=h.j4tx1z9j6ob8)

[**Docker Installation	14**](#_heading=h.nv0ifoz6xvj3)

[**Docker Commands	15**](#_heading=h.bhd1ekodnzs1)

[**THANK YOU!	21**](#_heading=h.4outra47xqg)


#
<a name="_heading=h.murz4unmeh9g"></a>

<a name="_heading=h.z0cn6abiswlz"></a>     **Introduction**

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.002.png)




Docker is a service which contains containers . it is derived for developers to develop, to run and execute applications. There is no need to install multiple operating systems. Also, docker is very flexible to work.

Docker is an open source software program or a service to manage containers, it enables us to create, run and execute softwares virtually without installing any other operating system. In short docker is an ecosystem where we can create and run containers. 

Docker has all the basic files and settings to run applications. This ability makes it easier, flexible & portable. We don't need to install a different OS in the base machine to run and execute an application program. We can create applications on it for every OS like: linux, mac, windows & e.t.c. docker is written in go language.

The Docker logo, with its whale graphic, symbolises the seamless packaging and transport of software applications, drawing a parallel with the efficiency of shipping containers in the physical world. The current Docker logo was introduced in June 2013.
# <a name="_heading=h.uq281eupo53k"></a> 
# <a name="_heading=h.kr2wgfm8q9cp"></a>**     
# <a name="_heading=h.v47wm74g426s"></a>**Architecture of Docker**

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.003.png)

**Docker client :** Docker users can interact with docker daemon through a client. 

- Docker client use command and rest API to communicate with the docker client 
- When a client runs any server command on the docker client terminal the client terminal sends these docker commands to the docker daemon. 

**Docker host :** Docker host is used to provide an environment to execute and run applications. 

- It contains the docker daemon ,image, container ,network and storage.

**Docker daemon :** Docker daemon runs on the host O/S.

- It is responsible for running containers  to manage docker services.
- Docker daemon can communicate with other daemon.

**Docker hub/Registry:** Docker registry manages and stores the docker images. 

**There are two types of registries**.

- **Public Registry:** It can be accessed by anyone and anywhere.
- **Private Registry:** It is used to share the image with the interpries.

**Docker image:** Docker images are the read only templates used to create docker containers.

Single file with all dependencies and configuration required to run the program. 

**Docker container:**  A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computer.



# <a name="_heading=h.4ute5o2aogdx"></a>**           
# <a name="_heading=h.dav0fcs3c99u"></a>            **Docker files**

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.004.jpeg)

Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line 


# <a name="_heading=h.wog901odjywz"></a>**Components of Dockerfile**

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.005.png)

# <a name="_heading=h.lv928ctft7yy"></a>   **Types of Docker Network**
#
<a name="_heading=h.2o6bcwy311ii"></a>The Docker network is a virtual network created by Docker to enable communication between Docker Containers. If two containers are running on the same host they can communicate with each other without the need for ports to be exposed to the host machine.

1. **Bridge:** If you build a container without specifying the kind of driver, the container will only be created in the bridge network, which is the default network. 
1. **Host:** Containers will not have any IP address they will be directly created in the system network which will remove isolation between the docker host and containers. 

1. **None:** IP addresses won’t be assigned to containers. These contaminants are not accessible to us from the outside or from any other container.

1. **Overlay:** overlay network will enable the connection between multiple Docker demons and make different Docker swarm services communicate with each other.


1. **ipvlan:** Users have complete control over both IPv4 and IPv6 addressing by using the IPvlan driver.



![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.006.png)



# <a name="_heading=h.1sgar3v90oe1"></a> **Docker Storage**

Containers don’t write data permanently to any storage location. Docker storage must be configured if you would like your container to store data permanently. The data doesn’t prevail when the container is deleted (using the remove command); this happens because when the container is deleted, the writable layer is also deleted. If the data is stored outside the container you can use it even if the container no longer exists.

`          `**Types of Docker Storage**

`  `**![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.007.jpeg)**

<a name="_heading=h.hdpna740xv7a"></a>


**Docker Volume**
======================================

- ## Docker volume is the most commonly used technology for the permanent storage of container data. 

- ## Docker volume is managed by Docker itself and has a dedicated filesystem on the host, and doesn't depend upon the filesystem structure on the host. 

- ## Docker volumes are explicitly managed via the Docker command line and can be created alone or during container initialization





|**Command**|**Description**|
| - | - |
|docker volume create|Create a volume|
|docker volume inspect|Display detailed information on one or more volumes|
|docker volume Is|List volumes|
|docker volume prune|Remove all unused local volumes|
|docker volume rm|Remove one or more volumes|

1. ## **Docker Bind Mount**

- Docker bind mount is the second **permanent storage** option but with more limited options than Docker volume.

- It can’t be managed via Docker CLI and is totally dependent on the availability of the filesystem of the host.

- A host filesystem can be created when running a container. Bind mounts are a sort of **superset of Volumes** (**named or unnamed**).



**Command:**

docker container run -v /host-path:/container-path image-name

1. ## ` `**tmpfs Mounts**


- tmpfs is a third storage option that is **not permanent** like Docker volume or bind mount.

- The data is written directly on to the host’s memory and deleted when the container is stopped.

**Command:**

docker run -d --name tmptest --mount type=tmpfs,destination=/app nginx:latest


<a name="_heading=h.j4tx1z9j6ob8"></a>

**Port Forwarding In Docker**
======================================

**Two types of Port Forwarding :-**   

Static Ports **:** You specify a fixed port on your computer (the host) for a service inside the Docker container.

**-p** is used for static port forwarding in docker.

Example: Put the web service from the container on port 8080 of my computer.



Dynamic Port : Docker chooses an available port on your computer for the service inside the container.

**-P** is use for dynamic port forwarding in docker

Example: Just find an open spot on my computer for the web service from the container.


# <a name="_heading=h.nv0ifoz6xvj3"></a>**     
# <a name="_heading=h.povnekg4qrga"></a> **Docker Installation**

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.008.png)

**Step1: Check if the system is up to date using the following command.**


|$ sudo apt-get update|
| - |

**Step2: Install Docker using the following command:**  



|$ sudo apt install docker.io|
| - |

**Step3: Add your local user to docker group so that user can run docker commands without sudo** 


|$ sudo groupadd docker|
| - |
|$ sudo usermod -aG docker $USER|

**Step4: Start the service of docker**

|$ sudo systemctl start docker|
| - |

**Step:5 Check the status of docker service**         



|$ sudo  systemctl status docker|
| - |

#
# <a name="_heading=h.i97zpatv2mas"></a><a name="_heading=h.bhd1ekodnzs1"></a>**Docker Commands**

1. **Check docker version**

`   `$ docker –version

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.009.png)

**2.**  **Check the container on the machine**

`     `$ sudo docker ps

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.010.png)

**3  Check docker images** 

`    `$   sudo docker images

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.011.png)

**4 Pull image from docker hub** 

`   `$ sudo docker pull ( image name )

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.012.png)



**5 Stop the container** 

`  `$ sudo  docker stop (container name )

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.013.png)

**6 Start the container** 

` `$ sudo docker start (container name )

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.014.png)

**7 Create the container**

` `$ sudo docker run -itd --name (container name ) (image name)

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.015.png)



**8 Bind Static port**

` `$ sudo docker run -itd  -p hostport:containerport --name (container name ) (image name)

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.016.png)

**9  How to enter in the container** 

$ sudo docker exec -it apache2 bash

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.017.png)


**10.   how to copy file in container** 



$ sudo docker cp index.html apache2:/usr/local/apache2/htdocs/

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.018.png)



**11.  Bind Dynamic Port**

$ sudo docker run -itd  -P  --name (container name ) (image name)

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.019.png)

**12.  mount file to a container**



$  sudo docker run -itd -p 8081:80 -v /var/www/html/index.html:/usr/local/apache2/htdocs/index.html  --name apache2 httpd

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.020.png)


**13. Remove the container**

$ sudo docker stop container name

$ sudo docker rm container name

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.021.png)

**14. Remove the Image**

$ sudo docker rmi (image name)

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.022.png)


**15. Create image from docker file**

- First create a dockerfile
- Build image with dockerfile

![](Aspose.Words.a92514bd-036b-4722-8719-d35376df72e6.023.png)







# <a name="_heading=h.4outra47xqg"></a>                      **THANK YOU!**  




