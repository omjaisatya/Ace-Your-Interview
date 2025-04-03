# **Docker Notes**

## **1. Introduction to Docker**

### **What is Docker?**

Docker is a containerization platform that allows developers to package applications with their dependencies into lightweight, portable containers.

### **Why Use Docker?**

- **Lightweight**: Containers share the host OS, making them more efficient than virtual machines.
- **Portable**: Runs the same way across different environments.
- **Scalable**: Supports microservices and CI/CD pipelines.
- **Fast Deployment**: Quick startup and consistent runtime.

---

## **2. Installing Docker**

### **Install on Linux (Ubuntu/Debian)**

```sh
sudo apt update
sudo apt install docker.io
```

### **Install on macOS (Using Homebrew)**

```sh
brew install --cask docker
```

### **Install on Windows**

- Download and install **Docker Desktop** from [Docker Official Website](https://www.docker.com/get-started).

---

## **3. Docker Architecture**

Docker follows a **client-server architecture** consisting of:

- **Docker Client**: Runs `docker` commands.
- **Docker Daemon**: Manages containers.
- **Docker Images**: Read-only templates for containers.
- **Docker Containers**: Running instances of images.
- **Docker Registry**: Stores and distributes images (e.g., Docker Hub).

---

## **4. Basic Docker Commands**

### **Check Docker Version**

```sh
docker --version
```

### **Verify Docker is Running**

```sh
docker info
```

### **Run a Test Container**

```sh
docker run hello-world
```

### **List Running Containers**

```sh
docker ps
```

### **List All Containers (Including Stopped)**

```sh
docker ps -a
```

### **Stop a Running Container**

```sh
docker stop <container_id>
```

### **Remove a Container**

```sh
docker rm <container_id>
```

---

## **5. Docker Images**

### **List Docker Images**

```sh
docker images
```

### **Pull an Image from Docker Hub**

```sh
docker pull ubuntu
```

### **Remove an Image**

```sh
docker rmi <image_id>
```

---

## **6. Running Containers**

### **Run a Container in Interactive Mode**

```sh
docker run -it ubuntu /bin/bash
```

### **Run a Container in Detached Mode (Background Mode)**

```sh
docker run -d nginx
```

### **Run a Container with Port Mapping**

```sh
docker run -p 8080:80 nginx
```

---

## **7. Dockerfile (Building Custom Images)**

### **What is a Dockerfile?**

A **Dockerfile** is a script containing instructions to build a Docker image.

### **Example Dockerfile**

```dockerfile
# Use an official Node.js runtime as a base image
FROM node:16

# Set the working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json ./
RUN npm install

# Copy the rest of the application
COPY . .

# Expose the application port
EXPOSE 3000

# Start the application
CMD ["node", "server.js"]
```

### **Building and Running an Image from Dockerfile**

```sh
docker build -t mynodeapp .
docker run -p 3000:3000 mynodeapp
```

---

## **8. Docker Compose**

### **What is Docker Compose?**

Docker Compose is a tool for defining and running multi-container applications. It uses a **docker-compose.yml** file.

### **Example `docker-compose.yml` File**

```yaml
version: "3"
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  app:
    build: .
    ports:
      - "3000:3000"
```

### **Running Docker Compose**

```sh
docker-compose up -d
```

### **Stopping Docker Compose**

```sh
docker-compose down
```

---

## **9. Docker Volumes (Data Persistence)**

### **List Docker Volumes**

```sh
docker volume ls
```

### **Create a Named Volume**

```sh
docker volume create mydata
```

### **Use a Volume in a Container**

```sh
docker run -v mydata:/app/data ubuntu
```

---

## **10. Docker Networking**

### **List Docker Networks**

```sh
docker network ls
```

### **Create a Custom Network**

```sh
docker network create mynetwork
```

### **Run a Container in a Specific Network**

```sh
docker run --network=mynetwork nginx
```

---

## **11. Docker Logs & Debugging**

### **View Logs of a Running Container**

```sh
docker logs <container_id>
```

### **Check Running Processes in a Container**

```sh
docker top <container_id>
```

### **Inspect a Container's Details**

```sh
docker inspect <container_id>
```

---

## **12. Docker Security Best Practices**

- Use official and minimal base images.
- Set **non-root users** in containers.
- Limit container privileges with **--cap-drop**.
- Enable **network segmentation** for security.
- Regularly scan images for vulnerabilities.

---

## **13. Docker Swarm (Container Orchestration)**

### **Initialize a Swarm Cluster**

```sh
docker swarm init
```

### **Deploy a Service in Swarm Mode**

```sh
docker service create --name web -p 80:80 nginx
```

### **List Swarm Services**

```sh
docker service ls
```

---

## **14. Kubernetes vs. Docker Swarm**

| Feature           | Docker Swarm | Kubernetes     |
| ----------------- | ------------ | -------------- |
| Complexity        | Easy         | Complex        |
| Scaling           | Fast         | Robust         |
| Networking        | Simple       | Advanced       |
| Load Balancing    | Built-in     | Requires Setup |
| Industry Adoption | Low          | High           |

---

## **15. Multi-Stage Builds**

### **What is a Multi-Stage Build?**

Multi-stage builds help reduce image size by using multiple `FROM` statements in a single `Dockerfile`.

### **Example: Multi-Stage Build for a Node.js App**

```dockerfile
# Stage 1: Build Stage
FROM node:16 AS builder
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . .

# Stage 2: Production Stage
FROM node:16-alpine
WORKDIR /app
COPY --from=builder /app .
CMD ["node", "server.js"]
```

### **Benefits**

- Reduces image size.
- Eliminates unnecessary dependencies in the final image.

---

## **16. Docker BuildKit (Faster Builds)**

Docker BuildKit improves build speed and caching.

### **Enable BuildKit**

```sh
export DOCKER_BUILDKIT=1
```

### **Use BuildKit in a Dockerfile**

```sh
# syntax=docker/dockerfile:1.2
```

### **Build an Image with BuildKit**

```sh
DOCKER_BUILDKIT=1 docker build -t myapp .
```

---

## **17. Docker Secrets (Secure Credentials Management)**

Docker Secrets allow secure storage of sensitive data like API keys and passwords.

### **Create a Secret**

```sh
echo "mysecretpassword" | docker secret create db_password -
```

### **List Secrets**

```sh
docker secret ls
```

### **Use a Secret in a Service**

```sh
docker service create --name mydb --secret db_password mysql
```

---

## **18. Docker System Prune (Cleanup Unused Data)**

### **Remove Stopped Containers, Unused Images, and Networks**

```sh
docker system prune -a
```

### **Remove All Unused Volumes**

```sh
docker volume prune
```

---

## **19. Dockerfile Best Practices**

- Use **alpine** base images for smaller image sizes.
- Minimize **layers** in the `Dockerfile`.
- **Sort COPY and RUN commands** to optimize caching.
- Use **.dockerignore** to avoid unnecessary files in the image.

### **Example `.dockerignore` File**

```plaintext
node_modules/
.env
.git
```

---

## **20. Docker Container Health Check**

### **Define a Health Check in Dockerfile**

```dockerfile
HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD curl -f http://localhost:3000 || exit 1
```

### **Check Container Health Status**

```sh
docker inspect --format='{{json .State.Health}}' <container_id>
```

---

## **21. Docker Image Scanning (Security Scans)**

### **Scan a Docker Image for Vulnerabilities**

```sh
docker scan myimage
```

---

## **22. Running Docker as a Non-Root User**

### **Create a User in Dockerfile**

```dockerfile
RUN groupadd -r myuser && useradd -r -g myuser myuser
USER myuser
```

---

## **23. Running Containers with Limited Resources**

### **Limit Memory Usage**

```sh
docker run --memory="512m" myapp
```

### **Limit CPU Usage**

```sh
docker run --cpus="1.5" myapp
```

---

## **24. Docker with Kubernetes (Basic Deployment)**

### **Create a Deployment YAML File (`deployment.yaml`)**

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  replicas: 2
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
        - name: myapp
          image: myimage:latest
          ports:
            - containerPort: 3000
```

### **Deploy to Kubernetes**

```sh
kubectl apply -f deployment.yaml
```

---

## **25. Docker Registry (Private Docker Hub Alternative)**

### **Run a Private Docker Registry**

```sh
docker run -d -p 5000:5000 --name registry registry:2
```

### **Push an Image to the Private Registry**

```sh
docker tag myimage localhost:5000/myimage
docker push localhost:5000/myimage
```

---

## **26. Docker Init System (Running Multiple Processes in One Container)**

By default, Docker containers should run a single process, but **tini** helps manage multiple processes.

### **Use `tini` in Dockerfile**

```dockerfile
FROM ubuntu
RUN apt-get update && apt-get install -y tini
ENTRYPOINT ["/usr/bin/tini", "--"]
CMD ["/bin/bash"]
```

---

## **27. Docker Debugging Tips**

### **Enter a Running Container’s Shell**

```sh
docker exec -it <container_id> /bin/sh
```

### **Check Container Network Connectivity**

```sh
docker network inspect bridge
```

### **Restart a Stopped Container**

```sh
docker restart <container_id>
```

---

## **28. Deploying Docker Containers with CI/CD (GitHub Actions)**

### **Example `docker-publish.yml` for GitHub Actions**

```yaml
name: Docker Build and Push

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Log in to Docker Hub
        run: echo "${{ secrets.DOCKER_PASSWORD }}" | docker login -u "${{ secrets.DOCKER_USERNAME }}" --password-stdin

      - name: Build and Push Docker Image
        run: |
          docker build -t mydockerhubuser/myapp:latest .
          docker push mydockerhubuser/myapp:latest
```
