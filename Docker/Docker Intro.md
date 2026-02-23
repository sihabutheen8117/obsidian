
### What is Hypervisor ? 

firmware that generally make virtualization possible. It simply creates virtualization layers that separates CPU/processors, [RAM](https://www.geeksforgeeks.org/computer-science-fundamentals/random-access-memory-ram/) and all other physical resources from virtual machines that we create.


- hypervisor is basically used by a virtual machine 
- it is virtualizes the hardware resources


### What is containarazation ? 

 - an OS-level virtualization method that packages an application and all its dependencies (code, runtime, libraries, configuration files) into a single, isolated, and executable unit called a container.
 - docker uses containerazation technique to run applications



### What is DockerHub

- Docker Hub is the world's largest container registry and cloud-based repository service provided by Docker, acting as a central library for finding, sharing, and storing container images

![[docker_host.webp]]



#  What is a Dockerfile?

A **Dockerfile** is a **text file with instructions** to build a Docker image.

It tells Docker:

- Which base OS to use
    
- Which software to install
    
- Which files to copy
    
- What command to run when container starts


# What is a Docker Image?

A **Docker Image** is a **read-only template** created from a Dockerfile.

It contains:

- OS
    
- Runtime (Node, Python, Java, etc.)
    
- Dependencies
    
- Your application code


## What is a Docker Container?

A **Docker Container** is a **running instance of an image**.

You start it like this:

docker run myapp

Now your application is running inside a container.

Container:

- Has its own file system
    
- Has its own network
    
- Is isolated from your system
    
- Can be stopped / started / deleted