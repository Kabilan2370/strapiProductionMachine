### 📦 Docker Overview & Key Concepts

🚀 1. Explain the problem Docker solves ?

Before installing any software we have to find out what operating system it runs on, what resources it needs, what other software it depends upon, is there any other software already installed that might interfere with the installation, and finally, how to install it. After installation comes the process of upgrading and maintaining the software. Computers have more than one application running. What if one application needs an upgrade in the dependency but another application runs on an older version of the dependency? Finally, when we want to remove a software we need to remember all the changes we had to do to install the software and then undo them after installation.

The gist is, the more software we use, the more difficult it becomes to manage and run them. Docker solves portability, consistency, speed, and ease of deployment by packaging everything into containers that run the same everywhere.
      
🖥️ 2. Difference between use of Virtual Machines vs Docker ?

Containers and virtual machines are very similar resource virtualization technologies. Virtualization is the process in which a system singular resource like RAM, CPU, Disk, or Networking can be ‘virtualized’ and represented as multiple resources. 

The key differentiator between containers and virtual machines is that virtual machines virtualize an entire machine down to the hardware layers and containers only virtualize software layers above the operating system level.

⚙️ 3. Understanding Docker Architecture -  What gets installed when Docker is installed ?

When Docker is installed, the primary component installed is the Docker Engine. The Docker Engine is a client-server application that consists of the following key elements:

  * Docker Engine REST API: This is the API that the Docker CLI (and other applications) use to communicate with the Docker Daemon. It defines the set of operations that can be performed on Docker objects.

  * Docker Daemon (dockerd): This is the server component of the Docker Engine. It's a persistent background process that manages Docker objects such as images, containers, networks, and volumes. It listens for Docker API requests and processes them, handling the heavy lifting of building, running, and managing Docker containers.

  * Docker CLI (Command Line Interface): This is the client component of the Docker Engine. The Docker CLI is a command-line utility that allows users to interact with the Docker Daemon. It's used to issue Docker commands (e.g., docker run, docker build, docker images) which are then sent to the Docker Daemon for execution.


📝 4. Dockerfile Deep Dive - Explain each line ?
      Why do we create or use a Dockerfile? To create a Docker container, we first need a Docker image. There are two ways to get a Docker image: one is by using the docker pull command to download images from Docker Hub, and the other is by using a Dockerfile to create our own Docker image.
A Dockerfile is a script composed of instructions that Docker uses to build an image. Each instruction creates a new layer in the image, contributing to the final image's structure.

There are 18 official Dockerfile commands available and mostly used by everyone.

1. FROM - Sets the base image. This should be the first line of dockerfile.

2. RUN - Executes commands during image build.

3. CMD - Specifies the default command to run when the container starts.

4. ENTRYPOINT - Defines the main executable for the container.

5. COPY - Copies files/directories from host to image.

6. ADD - Similar to COPY (also supports URL, archives extraction).

7. WORKDIR - Sets the working directory inside the container.

8. ENV - Sets environment variables.

9. ARG - Defines build-time variables.

10. EXPOSE - Documents the port the container listens on.

11. VOLUME - Creates a mount point for volumes.

12. USER - Sets the user to run commands inside the image.

13. LABEL - Adds metadata to the image.

14. HEALTHCHECK - Defines how Docker checks container health.

15. SHELL - Changes the default shell used for RUN commands.

16. STOPSIGNAL - Defines the signal used to stop the container.

17. ONBUILD - Adds a trigger instruction for child images.

18. MAINTAINER (deprecated) - Old way to specify the author (replaced by LABEL).


🛠️ 5. Key Docker Commands

📌 Image Commands

Action					Command

Build image				docker build -t myapp .
List images				docker images
Remove image			docker rmi image_id
Pull image				docker pull nginx

📌 Container Commands

Action					          Command

Run container			        docker run image
Run with port mapping		  docker run -p 8080:80 image
Start existing				    docker start con1(container_name)
Stop container			      docker stop con1(container_name)
See running containers		docker ps
See all containers			  docker ps -a
Remove container			    docker rm id
View logs				          docker logs id
Login into container			docker exec -it con1(container_name) /bin/bash


📌 System Commands

Action					Command

Removes unused Docker objects 		docker system prune
networks, and build cache) 
Displays Docker version info		  docker version
Displays system-wide information	docker info
regarding
information about                 docker inspect con1(container_name)
a Docker object	

🌐 6. Docker Networking

Docker networking allows containers to communicate with:

Each other

The host machine

External world

🔹 Types of Docker Networks

Docker Networking ?
.
Docker networking is the system that allows Docker containers to communicate with each other, with the Docker host, and with the outside world. It's a powerful feature that enables you to build complex, multi-container applications that are isolated yet interconnected.
1. bridge (default) - Used when you run containers normally

docker run --network bridge nginx

2. host - Uses host’s network, No port mapping required

docker run --network host nginx

3. none - No network

4. Overlay - This driver is used for multi-host networking and is the preferred choice for Docker Swarm services.

5. macvlan - This advanced driver allows you to assign a MAC address to a container, making it appear as a physical device on your network.


💾 7. Volumes & Persistence
        Volumes and Persistence in container orchestration (like Kubernetes/Docker) refer to how data survives beyond a container's lifecycle, with Volumes (Ephemeral) tied to the pod/container (gone when it dies) vs. Persistent Volumes (PVs) being cluster-managed storage (like NFS, cloud disks) that outlives pods, accessed via Persistent Volume Claims (PVCs), allowing stateful apps to retain data across restarts.

🔹 Volumes (Ephemeral)

Tied to the pod/container

Data is lost when the container/pod dies

Used for temporary storage or sharing between containers

🔹 Persistent Volumes (PVs)

Independent of pods

Data survives restarts or deletions

Usually backed by external storage (NFS, AWS EBS, etc.)

Key Differences
Feature	Volume	Persistent Volume (PV)
Lifecycle	Dies with pod	Lives at cluster level
Management	Defined in pod	Managed by admin / StorageClass
Data Survival	No	Yes
🧩 8. Docker Compose
        Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to manage the entire lifecycle of your application's services, networks, and volumes in a single YAML configuration file, typically named compose.yaml

🔹 Docker Compose Commands

Action	                Command

Start containers	      docker compose up
Rebuild & start	        docker compose up --build
Stop containers	        docker compose down
View logs	              docker compose logs



