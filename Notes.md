### CI/CD
Link: What Are CI/CD and the CI/CD Pipeline? (https://www.ibm.com/blog/ci-cd-pipeline/)

### Kernel and OS
https://www.quora.com/What-is-the-difference-between-a-kernel-and-an-operating-system

### Summary of differences: container vs. virtual machine [1]

| Characteristic| Container| Virtual machine|
| :---        |    :----:   |      ---: |
| Definition  |    Software code package containing an application’s code, its libraries, and other dependencies that make up the application running environment.|Digital replica of a physical machine. Partitions the physical hardware into multiple environments. |
| Virtualization [2]    | Virtualizes the operating system.       | Virtualizes the underlying physical infrastructure.   |
| Encapsulation   | Software layer above the operating system required for running the application or application component.        | Operating system, all software layers above it, multiple applications.      |

[1]:(https://aws.amazon.com/compare/the-difference-between-containers-and-virtual-machines/)

[2]: https://www.redhat.com/en/topics/virtualization/what-is-virtualization

### RESTful API [3]
1.1 API (Application Programming Interface) defines the rule you must follow to communicate with other software systems. It could be considered a gateway between client and resource.

1.2 REST (Representational State Transfer) is a software architecture that imposes conditions on how an API should work.

[3]: https://aws.amazon.com/what-is/restful-api/

### Docker Key Architecture [4]
Daemon (*dockerd*): It listens for Docker API requests and manager Docker object such as image.

Client (*docker*): is the primary way that many Docker users interact with Docker. 

Image: An image is a read-only template with instructions for creating a Docker container. For example, ubuntu is a image.

Container: Layers of images, eg. Base image alpine (small in size) ... application image (postgres)

*Notes: Container is running environment for image, including virtual file system(abstract of OS shared the same kernel), environment config, application image (postgres, redis...  ), port working behind talking to application running inside the container* 

Registry: A Docker registry stores Docker **images**.



[4]: https://docs.docker.com/get-started/overview/

### Shell
A command-line-interface (CLI) shell is a command interpreter for processing the command you enter to communicate with OS and kernel.

### API
A generic term defines the interface developers have to use when writing using libraries and programming language. **Kernel does not have API but ABI** [5].

### Kernel 
A kernel is a low level program interfacing with the hardware (CPU, RAM, disks, network, ...) on top of which applications are running.

[5]: https://stackoverflow.com/questions/12132260/what-is-the-difference-between-shell-kernel-and-api

### Port
A port is a virtual point where network connections start and end, ranging from 0 to 65,535: 0 - 1023 System/ Well-known ports; 1024 - 49151 User/ Registered ports; 49152 - 65535 Dynamic/ Personal use.r  

### Docker Practice
```Docker
docker run ubuntu 
# ubuntu is a distribution of Linux 
# use run instead of pull
docker run -it ubuntu
# it -- run interactively

root@c78446195a12:/# 
# root: highest privilege 
# c78446195a12: name of machine or id of container
#  / where we are; single / represents root directory  
# log in as root user 
```

### Docker Commands
- docker run -d xxx: It means docker runs in detached mode and allows me to close the opened terminal session without stopping the container. 

- Run two version of images which have the same port number

```Docker
docker run -p5000:5432 postgres:9.6
docker run -p5001:5432 postgres
```
 - docker start: restart the container 
  
  