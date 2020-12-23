
---

  

title: Docker File

  

description: Docker File

  

---
### DockerFile
---

**What is Dockerfile**
****

A ***Dockerfile*** is a text document that contains all the commands a user could call on the command line to assemble an image. 
Docker can build images automatically by reading the instructions from a Dockerfile. 
The Dockerfile provides the instructions to build a container image through the command :

**docker build -t [username/]<image-name>[:tag] <dockerfile-path>**

It starts from a previously existing Base image (through the FROM clause) followed by any other needed Dockerfile instructions.

---

**Example Dockerfile**

*This example creates a custom WildFly container with a custom administrative user. It also exposes the administrative port 9990 and binds the administrative interface publicly through the parameter ‘bmanagement’.*

---



    # Use the existing WildFly image
    FROM registry.connect.redhat.com/newrelic-openshift/java-agent

    # Add an administrative user
    RUN /opt/jboss/wildfly/bin/add-user.sh admin Admin#70365 --silent

    # Expose the administrative port
    EXPOSE 8080 9990

    # Bind the WildFly management to all IP addresses
    CMD [“/opt/jboss/wildfly/bin/standalong.sh”, “-b”, “0.0.0.0”,
    “-bmanagement”, “0.0.0.0”]

---

**List of instructions used in the Dockerfile**

| **Command**   |	**Description** |
| ------------- |   :-------------|
| FROM	        | Sets the base image for subsequent |
| MAINTAINER	| Sets the author field of the generated images  |
| RUN	        | Execute commands in a new layer on top of the current image and commit the results |
| CMD	        | Allowed only once (if many then last one takes effect) |
| LABEL	| Adds metadata to an image |
| EXPOSE	| Informs container runtime that the container listens on the specified network ports at runtime |
| ENV	| Sets an environment variable |
| ADD	| Copy new files, directories, or remote file URLs from into the filesystem of the container |
| COPY	| Copy new files or directories into the filesystem of the container |
| ENTRYPOINT	| Allows you to configure a container that will run as an executable |
| VOLUME	| Creates a mount point and marks it as holding externally mounted volumes from native host or other containers |
| USER	| Sets the username or UID to use when running the image |
| WORKDIR	| Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD commands |
| ARG	| Defines a variable that users can pass at build-time to the builder using --build-arg |
| ONBUILD	| Adds an instruction to be executed later, when the image is used as the base for another build |
| STOPSIGNAL | 	Sets the system call signal that will be sent to the container to exit |