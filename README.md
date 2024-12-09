This repository contains instructions and resources to:
1. Install Docker on Windows.
2. Pull and run a Hadoop container.
3. Build a custom Docker image with Fedora and Python.

## Contents
- [InstallDocker.md](./InstallDocker.md): Steps to install Docker on Windows.
- [HadoopContainer.md](./HadoopContainer.md): Steps to pull and run a Hadoop container.
- [Dockerfile](./Dockerfile): A Dockerfile for creating a Fedora-based Python image.
# Install Docker on Windows

1. Download Docker Desktop for Windows from the [official Docker website](https://www.docker.com/products/docker-desktop).
2. Install Docker Desktop by following the installation wizard.
3. After installation, start Docker Desktop and ensure that it's running.
4. Verify installation by running:
   ```bash
   docker --version
   ```

#### **HadoopContainer.md**
```markdown
# Pull and Run Hadoop Container

1. Pull the Hadoop image:
   ```bash
   docker pull sequenceiq/hadoop-docker
```
docker run -it sequenceiq/hadoop-docker /etc/bootstrap.sh -bash
```

#### **Dockerfile**
```dockerfile
# Base image
FROM fedora:latest

# Install Python
RUN dnf -y install python3 && \
    dnf clean all

# Default command
CMD ["python3"]
