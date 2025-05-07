# 🐳 Docker Architecture - Explained with Diagram

![Docker Architecture](path/to/your/image.png) <!-- Replace with your actual image path -->

---

## 🔹 Components of Docker Architecture

Docker architecture is divided into **three main components**:

---

### 1. **Client**

The Docker client is the interface through which users interact with Docker.

#### Common Commands:
- **`docker run`**  
  Runs a container from a specified image.

- **`docker build`**  
  Builds a Docker image from a Dockerfile.

- **`docker pull`**  
  Pulls an image from a Docker registry (e.g., Docker Hub).

> These commands communicate with the **Docker daemon** running on the Docker host.

---

### 2. **Docker Host**

The system where Docker is installed and running.

#### 🔧 Docker Daemon (`dockerd`)
- A background service that handles building, running, and managing Docker containers and images.
- Communicates with the client and registry.

#### 🗂️ Images
- Read-only templates used to create containers.
- Examples shown in diagram:
  - Python
  - Redis
  - Alpine (base image)

#### 📦 Containers
- Running instances of Docker images.
- Each container includes application code and dependencies.
- Containers are isolated and share the host OS kernel.

---

### 3. **Registry**

A storage and distribution system for Docker images.

#### 🔄 Images
- Public or private repositories.
- Examples from diagram:
  - NGINX
  - Ubuntu
  - PostgreSQL
  - Custom apps

#### ⚙️ Extensions
- Third-party tools to enhance Docker:
  - **JFrog** – Artifact management
  - **Portainer**, **Docker UI** – Web GUI for Docker management

#### 🔌 Plugins
- Extend Docker's core features:
  - Monitoring: **Grafana**
  - Networking: **Weave**, **VMware plugins**

---

## 🔁 Docker Workflow Summary:

1. The user issues a command from the **Client** (`build`, `run`, or `pull`).
2. The **Docker daemon** on the **Host** processes the request.
   - Builds new images from Dockerfiles.
   - Pulls images from the **Registry**.
   - Runs containers from images.
3. The daemon manages:
   - Local image storage
   - Running container instances
4. **Extensions** and **Plugins** enhance functionality for advanced use cases.

---

✅ **This architecture ensures lightweight, consistent, and portable application deployment across environments.**

