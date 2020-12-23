---

title: Docker

description: Docker

---
### Exploring Docker
  
---
  

 What is Docker
 
  

****

Docker is a software development tool and a virtualization technology that makes it easy to develop, deploy, and manage applications by using containers.

  

  

Container refers to a lightweight, stand-alone, executable package of a piece of software that contains all the libraries, configuration files, dependencies, and other necessary parts to operate the application.

****

  

  

 Difference between Docker and Virtual Machine

  

  

One of the popular approaches for running an application is over a virtual machine (VM). VMs run applications inside a guest operating system, which runs on virtual hardware powered by the server’s host OS.

  

  

![Docker architecture](_attachments/docker_docker-architecture.png  "Docker architecture")

  

  

Containers have a different approach to running applications. Containers do not include an operating system. Containers package the application binaries, utilize a host’s operating system, and share relevant libraries and resources as necessary to run applications.

  

  

*Table: Docker Vs Virtual Machines*

![Docker vs VM](_attachments/Docker-vs-VM.png  "Difference between Docker and VM")

****

 Why Containers ?

  

  

Containers provide the following benefits:

- Reduced IT management resources

- Reduced size of snapshots

- Quicker spinning up apps

- Reduced and simplified security updates

- Less code to transfer, migrate, and upload workloads

  

  

Unlike virtual machines, containers do not have high overhead and hence enable more efficient usage of the underlying system and resources.

The isolation and security aspects of Docker allow many containers to be run simultaneously on a given host. Once packaged, containers can be shipped and run anywhere.

  

  

Docker Architecture

  

  

Docker consists of a Docker Engine, which is a client server application. It contains the following components:

  

  

![Docker architecture](_attachments/docker_architecture.png  "Docker architecture")

  

  

- A server, which is a type of long-running program called a "daemon process". The daemon creates and manages Docker objects, such as images, containers, networks and volumes.

  

  

- A REST API, which specifies interfaces that programs can use to talk to the daemon and give it instructions.

  

  

- A command line interface (CLI) client (the Docker command line).

  

  

- The Docker client talks to the Docker daemon, which does the heavy lifting of building, running and distributing Docker containers.

  

  

- When a Docker command such as *docker run* is executed, the client passes on this command to the daemon process, which in turn carries them out.

  

  

Now let's understand container and Images briefly:

  

  

- Containers allow the packaging of your application (and everything that you need to run it) in a “container image”. Inside a container you can include a base operating system, libraries, files and folders, environment variables, volume mount-points, and your application binaries.

  

  

- A “container image” is a template for the execution of a container — It means that you can have multiple containers running from the same image, all sharing the same behavior, which promotes the scaling and distribution of the application. These images can be stored in a remote registry to ease the distribution.