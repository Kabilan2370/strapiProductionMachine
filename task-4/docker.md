📦 Docker Overview & Key Concepts
🚀 1. Problem Docker Solves

Before installing any software, we must consider:

Which operating system it supports

What resources it needs

What dependencies it requires

Whether existing software will conflict

How to install, upgrade, or uninstall it safely

As applications grow, this becomes harder.
Different apps may require different dependency versions, causing conflicts.
Removing an application also requires manually reversing all installation steps.

Docker solves these issues by packaging applications into isolated containers that include everything they need. This guarantees:

Portability (runs the same everywhere)

Consistency

Fast deployment

Simplified maintenance

🖥️ 2. Virtual Machines vs Docker
Aspect	Virtual Machines	Docker Containers
Virtualization Level	Entire hardware (system-level)	OS-level (software only)
Size	Heavy (GBs)	Lightweight (MBs)
Boot Time	Slow (minutes)	Fast (seconds)
Isolation	Strong (full OS isolation)	Process-level isolation
Resource Usage	High	Very low

Key Difference:

VMs virtualize hardware.

Containers virtualize only software layers above the OS.

⚙️ 3. Docker Architecture — What Gets Installed?

When Docker is installed, the following components are included:

🔹 Docker Engine

A client–server application containing:

1. Docker Daemon (dockerd)

Core service running in the background

Manages images, containers, networks, and volumes

Executes Docker API requests

2. Docker Engine REST API

Interface used by Docker CLI and other tools

Defines operations on Docker objects

3. Docker CLI

Command-line tool for interacting with Docker

Example commands: docker run, docker build, etc.

📝 4. Dockerfile Deep Dive

Why use a Dockerfile?
To create a container, we need a Docker image.
Two ways to get an image:

Pull from Docker Hub → docker pull image

Build our own using a Dockerfile

A Dockerfile is a script containing instructions to build custom images.

🔹 18 Dockerfile Commands

FROM – Base image

RUN – Execute commands during build

CMD – Default container command

ENTRYPOINT – Main container executable

COPY – Copy files into image

ADD – Like COPY (supports URLs + extraction)

WORKDIR – Set working directory

ENV – Set environment variables

ARG – Build-time arguments

EXPOSE – Document container port

VOLUME – Create mount point

USER – Set running user

LABEL – Add metadata

HEALTHCHECK – Container health test

SHELL – Change default shell

STOPSIGNAL – Signal to stop container

ONBUILD – Trigger for child images

MAINTAINER (Deprecated) – Old author field

🛠️ 5. Key Docker Commands
📌 Image Commands
Action	Command
Build image	docker build -t myapp .
List images	docker images
Remove image	docker rmi image_id
Pull image	docker pull nginx
📌 Container Commands
Action	Command
Run container	docker run image
Run with port mapping	docker run -p 8080:80 image
Start container	docker start con1
Stop container	docker stop con1
List running containers	docker ps
List all containers	docker ps -a
Remove container	docker rm id
View logs	docker logs id
Login to container	docker exec -it con1 /bin/bash
📌 System Commands
Action	Command
Remove unused resources	docker system prune
Docker version	docker version
System info	docker info
Inspect object	docker inspect con1
🌐 6. Docker Networking

Docker networking allows containers to communicate with:

Each other

The host machine

External world

🔹 Types of Docker Networks

Bridge (default)

docker run --network bridge nginx


Host

Shares host network

No port mapping required

docker run --network host nginx


None

No network access

Overlay

Multi-host networking for Docker Swarm

Macvlan

Assigns a MAC address to a container

💾 7. Volumes & Persistence
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

Docker Compose is used to manage multi-container applications using a single compose.yaml.

🔹 Docker Compose Commands
Action	Command
Start containers	docker compose up
Rebuild & start	docker compose up --build
Stop containers	docker compose down
View logs	docker compose logs

